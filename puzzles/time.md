# Time

These puzzles count time and trigger time-based events.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#after)

**"after"**

Waits for a specified amount of time and then triggers puzzles placed inside the "do" slot.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-after.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#every)

**"every"**

Waits for a specified amount of time and then triggers puzzles placed inside the "do" slot. Then repeats.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-every.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#every_frame)

**"every frame"**

Triggers puzzles placed inside the "do" slot every rendering frame \(normally at the rate of 60 frames per second\).![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-every-frame.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#elapsed_delta)

**"elapsed delta"**

Outputs the amount of time \(in seconds\) passed from the previous rendering frame. Can be used with the "every frame" puzzle to implement frame-independent animation.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-elapsed-delta.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#elapsed_total)

**"elapsed total"**

Outputs the amount of time \(in seconds\) passed from the application start. Can be used with the "every frame" puzzle to implement procedural animation and various visual effects.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-elapsed-total.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#set_timer)

**"set timer"**

Waits for a specified amount of time and then triggers puzzles placed inside the "do" slot. The specified ID can be used to override or remove the timer.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-set-timer.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#remove_timer)

**"remove timer"**

Removes a previosly set timer by using its ID.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-remove-timer.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Time.html#get_date_time)

**"system date / time"**

Get system date and time. Enable UTC checkbox in order to get time of the UTC/GMT zone instead of the local time zone.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-get-date-time.jpg)

