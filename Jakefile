var stylus = require('stylus')
    , fs = require('fs');

desc('Compile');
task('default', function (params) {

  var str = fs.readFileSync(__dirname + '/aristo/index.styl', 'utf8');

  stylus(str)
    .set('filename', __dirname + '/aristo/index.styl')
    // Don't inline images for now, they're too big
    //.define('url', stylus.url({ paths: [__dirname + '/images'], limit: 50000 }))
    .render(function(err, css){

      if (err) throw err;

      fs.writeFile('aristo.css', css, function (err) {
        if (err) throw err;
        console.log('Compiled!');
      });
  });

});
