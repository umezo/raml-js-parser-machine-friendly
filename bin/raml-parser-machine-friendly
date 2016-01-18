#!/usr/bin/env node

'use strict';

var resolve = require('path').resolve;
var raml = require('raml-parser');

var filename = process.argv[2];

if (!filename) {
  console.error('No filename specified');
  console.error('Usage: `raml-parser-machine-friendly api.raml`');

  process.exit(1);
}


raml.loadFile(resolve(process.cwd(), filename))
  .then(function (raml) {})
  .catch(function (err) {
    console.log("Context:" + err.context);
    console.log("Message:" + err.message);
    console.log("File:" + err.problem_mark.name);
    console.log("Line:" + err.problem_mark.line);
    console.log("Column:" + err.problem_mark.column);

    process.exit(1);
  });
