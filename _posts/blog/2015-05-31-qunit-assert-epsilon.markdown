---
layout: post
title: "QUnit Assert Equality with Machine Epsilon"
date: 2015-06-01 19:05:00
author: Ed Oswald Go
categories:
- blog
- JavaScript
- Unit Testing
img: qunit-assert-epsilon.png
---

###Overview
Unit testing is a great process for producing high-quality software when done correctly. I am a developer that is not used to creating test cases for automated testing or develop software via Test / Behaviour Driven Development. Little by little, I want to be a developer that is very productive even by using TDD / BDD. 

I recently tried adding [QUnit][qunit] to my [Stock Profit Calculator][stock-calc] project in order to explore unit testing in JavaScript. Integration with [QUnit][qunit] is a breeze as the quick start guide is simple and easy to understand.

HTML Code (*test.html*):

        <!DOCTYPE html>
        <html>
        <head>
          <meta charset="utf-8">
          <title>QUnit Example</title>
          <link rel="stylesheet" href="http://code.jquery.com/qunit/qunit-1.18.0.css">
        </head>
        <body>
          <div id="qunit"></div>
          <div id="qunit-fixture"></div>
          <!-- CDN -->
          <script src="http://code.jquery.com/jquery-1.11.3.min.js"></script>
          <script src="http://code.jquery.com/qunit/qunit-1.18.0.js"></script>
          <script src="http://cdnjs.cloudflare.com/ajax/libs/mathjs/1.6.0/math.min.js"></script>
          <!-- Libraries to be tested -->
          <script src="../js/broker.js"></script>
          <script src="../js/brokers/broker-col.js"></script>
          <script src="../js/stock.calculator.js"></script>
          <!-- Test Suites -->
          <script src="../js/test/tests.js"></script>
        </body>
        </html>

JavaScript Code (*tests.js*):

        (function() {
          QUnit.test( "hello test", function( assert ) {
            assert.ok( 1 == "1", "Passed!" );
          });
        })();

###Problem
As I ran my created test suite, I encountered an error when comparing the equality of two floating point numbers. Based on the example below, *0.3333* is really not equal to *0.33333333333333333333* because of the decimal places. One approach I tried is to round the number to four decimal places in order to be equal to *0.3333*. But, this approach will not solve all rounding cases. I checked QUnit's core API and there's no method with epsilon support. How did I solve my problem?

        QUnit.test( "Test Equality", function( assert ) {
          assert.equal( 1/3, 0.3333);
        });

![alt text](/assets/img/blog/qunit-assert-epsilon/qunit-assert-problem-1.png "QUnit Assert Problem #1")

###Solution
My initial plan is to extend QUnit to support an epsilon parameter to some of its methods. But luckily, I encountered a [QUnit plugin][qunit-plugins], named [Close][qunit-assert-close], that already addressed the problem stated above.

I used the `assert.close(actual, expected, maxDifference, message);` function of the plugin wherein the function accepts an additional parameter, `maxDifference`. The `maxDifference` parameter is the epsilon that tolerates the difference between the actual and expected output.

        QUnit.test( "Test Equality with Machine Epsilon", function( assert ) {
          assert.close( 1/3, 0.3333, 0.00005);
        });

![alt text](/assets/img/blog/qunit-assert-epsilon/qunit-assert-solution-1.png "QUnit Assert Solution #1")

Thank you.


[qunit]: https://qunitjs.com/
[qunit-plugins]: https://qunitjs.com/plugins/
[qunit-assert-close]: https://github.com/JamesMGreene/qunit-assert-close
[stock-calc]: /project/stock-profit-calculator/