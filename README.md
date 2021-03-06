VideoBufferReader
=================

A simple usage library, that allows you to read video samples (CMSampleBufferRef), that you can easily convert to images, for face detecting, motion detecting and more!

#### Usage

1) Add **AVFoundation.framework** to your project 

2) Create an instance (use designated initializer or forget to assign delegate)

	BufferReader *bufferReader = [[BufferReader alloc] initWithDelegate:self];
	
3) Implement protocol methods to recieve samples, errors if occured and get finish callback;

	- (void)bufferReader:(BufferReader *)reader didFinishReadingAsset:(AVAsset *)asset;
	- (void)bufferReader:(BufferReader *)reader didGetNextVideoSample:(CMSampleBufferRef)bufferRef;
	- (void)bufferReader:(BufferReader *)reader didGetErrorRedingSample:(NSError *)error;

4) Create AVAsset with link to your video file

	AVAsset *asset = [AVAsset assetWithURL:#URL_PATH_TO_VIDEO];
	
5) Start reading samples by toggling 

	[bufferReader startReadingAsset:asset error:&error];
* * *

Library supports ARC, if you want to use it in project, that doesn't support ARC, don't forget to add **-fobjc-arc** flag

* * *
	
In future releases I planned to implement audio samples support.

* * *

If you have any questions, please feel free to interact.
My e-mail <purpleshirted@gmail.com>

Copyright (c) 2014 Vitaliy Malakhovskiy. All rights reserved.