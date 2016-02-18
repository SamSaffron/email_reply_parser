# DEPRECATED

This library is deprecated. Please see instead:

https://github.com/discourse/email_reply_trimmer

----------

# Email Reply Parser

[![Build Status](https://secure.travis-ci.org/lawrencepit/email_reply_parser.png?branch=master)](http://travis-ci.org/lawrencepit/email_reply_parser)
[![Code Climate](https://codeclimate.com/badge.png)](https://codeclimate.com/github/lawrencepit/email_reply_parser)
[![Gem Version](https://fury-badge.herokuapp.com/rb/email_reply_parser.png)](http://badge.fury.io/rb/email_reply_parser)

EmailReplyParser is a small library to parse plain text email content.

This is what GitHub uses to display comments that were created from
email replies.  This code is being open sourced in an effort to
crowdsource the quality of our email representation.

## Usage

To parse reply body:

`parsed_body = EmailReplyParser.parse_reply(email_body, from_address)`

Argument `from_address` is optional. If included it will attempt to parse out signatures based on the name in the from address (if signature doesn't have a standard deliminator.)

## Installation

Get it from [GitHub][github] or `gem install email_reply_parser`.  Run `rake` to run the tests.

[github]: https://github.com/github/email_reply_parser

## Contribute

If you'd like to hack on EmailReplyParser, start by forking the repo on GitHub:

https://github.com/github/email_reply_parser

The best way to get your changes merged back into core is as follows:

* Clone down your fork
* Create a thoughtfully named topic branch to contain your change
* Hack away
* Add tests and make sure everything still passes by running rake
* If you are adding new functionality, document it in the README
* Do not change the version number, I will do that on my end
* If necessary, rebase your commits into logical chunks, without errors
* Push the branch up to GitHub
* Send a pull request to the `github/email_reply_parser` project.

## Known Issues

### Quoted Headers

Quoted headers like these currently don't work with other languages:

    On <date>, <author> wrote:

    > blah

### Weird Signatures

Not everyone follows this convention:

    Hello

    Saludos!!!!!!!!!!!!!!
    Galactic President Superstar Mc Awesomeville
    GitHub

    **********************DISCLAIMER***********************************
    * Note: blah blah blah                                            *
    **********************DISCLAIMER***********************************

