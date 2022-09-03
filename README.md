# Vector-animation
Vector graphic animations used in my MusicPlayer application

# Use in Android Studio
1. Repeat same animation
  * Add animation file to drawable resource folder
  * Set drawable as background in layout-File
    android:background="@drawable/anim_skip_forward"
  * Trigger animation in code:
  
        AnimatedVectorDrawable animatedVectorDrawable = (AnimatedVectorDrawable) 'view to animate'.getBackground();
        animatedVectorDrawable.start();
        
2. Use animation to switch state:
  * Use animation drawables to switch between states:
  
        public void setControlButton(boolean isOnPause) {
            if (!isOnPause) {
              //Stop playback
              control.setBackground(ContextCompat.getDrawable(requireContext(), R.drawable.play_to_pause_anim));
              AnimatedVectorDrawable animatedVectorDrawable = (AnimatedVectorDrawable) control.getBackground();
              animatedVectorDrawable.start();
            } else {
              //Start playback
              control.setBackground(ContextCompat.getDrawable(requireContext(), R.drawable.pause_to_play_anim));
              AnimatedVectorDrawable animatedVectorDrawable = (AnimatedVectorDrawable) control.getBackground();
              animatedVectorDrawable.start();
            }
        }
