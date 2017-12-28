# audio_sequence 0.1 beta
### jQuery based script that allows you to control, monitor and play multiple audio files in sequences at a time.

## Major features:
- Repeat whole: allows you to repeat a list of audio files as whole for a given number of repeats
- Repeat each: allows you to repeat each file of list of audio files for a certain number of repeats
- Repeat forever: allows you to repeat a list of audio files as whole forever !
- Repeat delay: allows you to add a delay in-between repeats
- Log: gives music player like interface from the console

### Setup:
```javascript
<script src='audio_sequence.js' type='text/javascript'></script>
<script type='text/javascript'>
  player = audio_sequence({
    files: ['1.mp3', '2.mp3', '4.mp3'],
    repeat_forever: 'true'
  })
</script>
```

### Options:
```javascript
this.options = {
  files: [], // audio files inserted will be stored in
  repeats: 0, // number of repeats to obey with some adjustments later
  repeat_whole: 'true', // repeat all files as whole for the number of repeats
  repeat_each: 'false', // repeat each file for the number of repeats [You can not select both !]
  repeat_forever: 'false', // to keep repeating endlessly, only works on repeat whole
  repeat_delay: 0, // to add a time delay between each repeat in seconds
  reverse_order: 'false', // to reverse the order list of audio files
  shuffle_order: 'false', // to randomly shuffle the order of the files list
  auto_start: 'true', // to auto start playing as the module loads
  cleanup: 'true' // to clean up after existing
}
```

### Useful functions:
#### To use any of the following functions, you have to get an instance of the constructer, which we did in the Setup section :
` player = audio_sequence()` </br>
` player.following_functions()`

#### - Play list :
```javascript
this.playlist = function playlist (check) {
  // to log the list of audio elements and their properties
}

this.log = function log (doornot) {
  // to a live list of the playing elements and quit whenever done playing
}

this.list = function list (onlyPlaying = false) {
  // to return html ready list of elments
}
```

#### - List order :
```javascript
this.shuffle = function shuffle () {
  // picking items from the array randomly and reinserting them, to create shuffle like effect
}

this.reverse = function reverse () {
  // to reverse the order of elements ID list
}
```

#### - Control audio:
- List of typical music player like functions

```javascript
this.replay = function replay () {}

this.stop = function stop () {
    // to stop playing all unended elements
}

this.pause = function pause () {
  // to pause the currently played element
}

this.resume = function resume () {
  // to resume the currently paused element
}

this.previous = function previous () {
  // to move the list of elements backward to play previous element
}

this.next = function next () {
  // moving the list of elements forward by one element, to play next element
}

this.forward = function forward (seconds) {
  // to forward the duration of audio element with seconds or portion of it
}

this.backward = function backward (seconds) {
  // to forward the duration of audio element with seconds or portion of it
}

this.mute = function mute () {
  // to mute all audio elements
}

this.unmute = function unmute () {
  // to unmute all audio elements
}
```

#### - Manage files:

```javascript
this.add_file = function addFile (file) {
  // adding an audio file into the playing lis
}

this.remove_file = function removeFile (id) {
  // remove file using ID index number, file nASes can mismatch but ids not
}
```

#### - Cleanup and exit:

```javascript
this.abort = function abort () {
  // make sure all created elements events are off
}

this.empty = function empty () {
  // to remove created audio elements from the DOM
}

this.exit = function exit (msg = true) {
  // to gracefully exist, with a thorough cleanup
}
```