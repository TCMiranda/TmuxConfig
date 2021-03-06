# My Tmux General Configurations
## Global
  
  set -g default-terminal "screen-16color"
  setw -g mode-keys emacs

## utf8 support

  set-window-option -g utf8 on

## Mouse on

  setw -g mode-mouse off
  set -g mouse-select-pane off
  set -g mouse-resize-pane on
  set -g mouse-select-window off

## Bind reload conf
  
  bind R source-file ~/.tmux.conf \; display-message " Config reloaded.."

## Status bar

  set -g status-bg black
  set -g status-fg brightwhite
  set -g status-left '#[fg=white]#H'

  set-option -g status-position top

## Highlight active window
  
  set-window-option -g window-status-current-bg white

## Automatically set window title

  set-option -g allow-rename off
  set-option -g set-titles on

  set-option -g set-titles-string '#S:#I.#P #W'
  set-option -g set-titles-string "tmux.#I.#W"
  set-window-option -g automatic-rename off

## The position of the window list (left, centre, or right).
  
  set-option -g status-justify left

## Update the status bar every n seconds.

  set-option -g status-interval 5

## The maximum length of the left component of the status bar.

  set-option -g status-left-length 20

## The maximum length of the right component of the status bar.

  set-option -g status-right-length 20

## Status bar format.

  set-option -g status-left ''
  set-option -g status-right '#[fg=green] ###S#[default]'

## border colours

  set -g pane-border-style fg=black
  set -g pane-active-border-style fg=blue
  set -g pane-active-border-style bg=default
  
## Clock

  set-window-option -g clock-mode-colour cyan
  set-window-option -g clock-mode-style 24

## List of plugins

  set -g @tpm_plugins '              \
    tmux-plugins/tpm                 \
    tmux-plugins/tmux-sensible       \
    tmux-plugins/tmux-yank           \
    tmux-plugins/tmux-copycat        \
    tmux-plugins/tmux-sensible       \
    tmux-plugins/tmux-open           \
    tmux-plugins/tmux-sidebar        \
    tmux-plugins/tmux-resurrect      \
  '

### Initializes TMUX plugin manager.
### Keep this line at the very bottom of tmux.conf.

  run-shell '~/.tmux/plugins/tpm/tpm'
