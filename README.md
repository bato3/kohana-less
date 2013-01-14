kohana-less
===========

Module for Kohana with double the cache (server side and the browser side)

Instalation
-----------
First enable modile in bootstrap.php

Update config ``lessphp.php``

` return array(
    /**
      * default files set
      */
    'default' =>'default',
    /**
      File extension for one file
      */
    'ext' => 'less',
    /**
      Cache config, `FALSE` for disable
      */
    'cache'=> 'lessphp',
    
    'basedir' => APPPATH.'assets'.DIRECTORY_SEPARATOR,
    /**
        Files to default (empty) route.
      */
    'sets' => array(
      'default' => array(
        'test.less',
        ),
     ),
  );
`

Usage
-----

Default stylesheet from config:

  `<?=Lessphp::style()?>`
  
Named stylesheet from config:

  `<?=Lessphp::style('config set name')?>`
  
One or more files:

  `<?=Lessphp::style('file.less')?>
  <?=Lessphp::style(Array('file.less','file.less'))?>`
  
  
Similar usage in php code:

  `$template->stylesheets[] = Lessphp::url();
  $css = Lessphp::compile_file();`
