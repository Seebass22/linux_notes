# add a sink (to record an application)
pacmd load-module module-null-sink sink_name=MySink
pacmd update-sink-proplist MySink device.description=MySink

# add a loopback device (to record mic)
pacmd load-module module-loopback sink=MySink

# remove loopback
pacmd unload-module module-loopback

# monitor null-sink (to record and listen at the same time)
pacmd load-module module-loopback sink=$output_sink source=MySink.monitor

# combine 2 sinks (to record and listen at the same time
pacmd load-module module-combine sink_name=combiled slaves=$headphones,MySink
