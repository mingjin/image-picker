fs = require 'fs'

{print} = require 'sys'
{spawn} = require 'child_process'

build = (callback) ->
  coffee = spawn 'coffee', ['-c', '-o', 'image-picker', 'source/coffee']
  coffee.stderr.on 'data', (data) ->
    process.stderr.write data.toString()
  coffee.stdout.on 'data', (data) ->
    print data.toString()
  coffee.on 'exit', (code) ->
    callback?() if code is 0

uglify = (callback) ->
  
  
task 'build', 'Build image-picker/ from source/coffee', ->
  build()
  
task 'uglify', 'Minify and Uglify image-picker javascripts', ->
  uglify()