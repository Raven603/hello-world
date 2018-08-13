# This is a copy of my current crontab. To install it, you can use:
# crontab -u dantasse ./crontab
# 
# Each task to run has to be defined through a single line
# indicating with different fields when the task will be run
# and what command to run for the task
# 
# To define the time you can provide concrete values for
# minute (m), hour (h), day of month (dom), month (mon),
# and day of week (dow) or use '*' in these fields (for 'any').
# Notice that tasks will be started based on the cron's system
# daemon's notion of time and timezones.
# 
# Output of the crontab jobs (including errors) is sent through
# email to the user the crontab file belongs to (unless redirected).
# That is, for example, /var/mail/dantasse
# # m h  dom mon dow   command

00 00 * * * cd /home/hzn/scrape_social_media_in_area && . env/bin/activate && ./print_table_counts.py >> /home/hzn/pg_log.txt
12 0-23/6 * * * cd /home/hzn/scrape_social_media_in_area && . env/bin/activate && python ./notify_if_broken.py
00 07 * * * cd /home/hzn/scrape_social_media_in_area && ./backup.sh >> backup.log


