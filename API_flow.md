#API: work flow

# API workflow #

The class offers the developer an API to easy implement this in your app.
You should respect a certain flow:

  1. Make an instance of the class, it’s a singleton class, so just ask for the instance:
`var recorder:FLVRecorder=FLVRecorder.getInstance()`

> 2 Define the target FLV-file’s properties, the file instance to your flv-file, width & height, framerate and the systemManager instance, that’s a Flash internal declared variable and the optional duration in seconds:
`file=File.desktopDirectory.resolvePath(“recording.flv”);`
`recorder.setTarget(file,640,480,fps,systemManager, durationInSeconds)`

the duration is optional, it will be automaticly filled in when left blank.

> 3 Insert some bitmaps, bitmapdatas or a screenshot of a component into the flv-file:
```
recorder.captureComponent(vidDisplay)	  //DisplayObject, takes a screenshot from that component
recorder.saveFrame(bmpdata)   //Bitmapdata, does nothing with it
recorder.saveSmoothedBitmapFrame(bmp)   //Bitmap, smooths before saving
recorder.saveSmoothedFrame(bmpdata)  //Bitmapdata, smooths bitmapdata before saving
```

> 4  To stop recording, simply command the class to stop, it will start to convert your saved data to the flv-file
`recorder.stopRecording()`

It will throw 3 events, when saving starts, when savings stops and one while saving to pass on the savings progress
  * FLVRecorderEvent.FLV\_START\_CREATION
  * FLVRecorderEvent.FLV\_CREATED
  * FLVRecorderEvent.PROGRESS //event contains progress property, is a value between 0-1 to indicate progress

> 5 All done, that’s how simple things can be in life.

> 6 Test it, use it and give me feedback of your experiences!