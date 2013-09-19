Da2nFlickr
==========

Get your flickr photos


EXAMPLE : 
```
<?php
$flickrapi 		= YOUR_FLICKR_API_KEY;
$flickrsecret	= YOUR_FLICKR_SECRET_KEY;
$flickrid 		= YOUR_FLICKR_ID;
$flickrlimit	= 10 ;
$flickpaged		= 1 ;

$f 		= new da2nFlickr( $flickrapi, $flickrsecret );
$recent = $f->people_getPublicPhotos( $flickrid, NULL, 'views', $flickrlimit, $flickpaged );
?>
<section class="flickr-container">
	<h2 class="title-page">Flickr Title</h2>
	<div class="flickr">
		<?php 
		foreach ( $recent['photos']['photo'] as $photo ) :
		$urlimg		= $f->buildPhotoURL($photo,"small");
		$urlimgori	= $f->buildPhotoURL($photo,"original");
		?>				
			<a href="<?php echo $urlimgori;?>">
				<img src="<?php echo $urlimg; ?>" />
			</a>
		<?php 
		endforeach;
		?>
	</div><!-- .flickr -->
</section><!-- .flickr-container -->
```
