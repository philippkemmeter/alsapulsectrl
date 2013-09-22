# aslapulsectrl

Simple command line tool to control your audiopulse+alsa device perctly suited
to be used in other script e.g. for acpi button binding.

## Synopsis

    Usage: /usr/local/bin/alsapulsectrl [options] (get)|(set|inc|dec VOLUME)
    
    Returns or modifies the volume of pulse audio sink 0.
    
    Available options:
      -p        If set, the passed and returned volume is in
                percent having 65535 defined as 100%.
                Otherwise the volume is absolute.
                This effects both VOLUME as well as the
                output of this tool.
      -h,--help Prints this help and exits.

## Examples

    # increase by 10%
    alsapulsectrl -p inc 10

    # decrease by 2304
    alsapulsectrl dec 2304

    # set to 130%
    alsapulsectrl -p set 130

    # echos current volume
    alsapulsectrl get

    # echos current volume in percent
    alsapulsectrl get -p

## Requirements

This tool uses `amixer` and `pacmd`. The first is part of the `alsa-utils`
package, the latter of `pulseaudio`.
