#How–to-use code example.

# How–to-use code example #
A small example of how to use this class:

```
private var tmr:Timer
private var recorder:FLVRecorder
private var file:File

private function startRecording():void{

 if(recorder==null){
 recorder=FLVRecorder.getInstance()
 }
 file=File.desktopDirectory.resolvePath(“recording.flv”);
 recorder.setTarget(file,640,480,fps,systemManager)

 if(tmr==null){
 tmr=new Timer(1000/fps)
 }
 tmr.addEventListener(TimerEvent.TIMER,record)
 tmr.start()
}

private function record(e:TimerEvent):void{
 recorder.captureComponent(vidDisplay)	 //DisplayObject
 //recorder.saveFrame(bmpdata)  //Bitmapdata
 //recorder. saveSmoothedBitmapFrame(bmp)  //Bitmap
 //recorder. saveSmoothedFrame(bmpdata)  //Bitmapdata
}

private function stopRecording():void{
 tmr.stop()

 //when saving is done
 recorder.addEventListener(FLVRecorderEvent.FLV_CREATED,fileMade)

 //when saving starts
 recorder.addEventListener(FLVRecorderEvent.FLV_START_CREATION,startCreatingFLV)

 recorder.stopRecording()
}

private function startCreatingFLV(e:FLVRecorderEvent):void{
 recorder.addEventListener(FLVRecorderEvent.PROGRESS,onFLVCreationProgress)
}

private function onFLVCreationProgress(e:FLVRecorderEvent):void{
 //e.progress: percent complete (0 to 1)
 //pbSaving: ProgressBar component in Flex
 pbSaving.setProgress(e.progress,1)
}
```