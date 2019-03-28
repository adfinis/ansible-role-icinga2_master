#!/usr/bin/env bash

account_sid="{{ icinga2_master_twilio_account_sid }}"
auth_token="{{ icinga2_master_twilio_auth_token }}"
phone_number="{{ icinga2_master_twilio_phone_from }}"
application_sid="{{ icinga2_master_twilio_phone_application_sid }}"

PROG="`basename $0`"
ICINGA2HOST="`hostname`"

## Function helpers
Usage() {
cat << EOF

Required parameters:
  -r USERPHONE (\$user.pager\$)
EOF
}

Help() {
  Usage;
  exit 0;
}

Error() {
  if [ "$1" ]; then
    echo $1
  fi
  Usage;
  exit 1;
}

urlencode() {
  local LANG=C i c e=''
  for ((i=0;i<${#1};i++)); do
    c=${1:$i:1}
    [[ "$c" =~ [a-zA-Z0-9\.\~\_\-] ]] || printf -v c '%%%02X' "'$c"
    e+="$c"
  done
  echo "$e"
}

## Main
while getopts hr: opt
do
  case "$opt" in
    h) Help ;;
    r) USERPHONE=$OPTARG ;; # required
   \?) echo "ERROR: Invalid option -$OPTARG" >&2
       Error ;;
    :) echo "Missing option argument for -$OPTARG" >&2
       Error ;;
    *) echo "Unimplemented option: -$OPTARG" >&2
       Error ;;
  esac
done

shift $((OPTIND - 1))

## Keep formatting in sync with mail-service-notification.sh
for P in USERPHONE ; do
	eval "PAR=\$${P}"

	if [ ! "$PAR" ] ; then
		Error "Required parameter '$P' is missing."
	fi
done

## Send the sms using the Twilio API
echo "sent call to ${USERPHONE} now: $(date -u)" >> ./logfile.log

curl -X POST \
  https://api.twilio.com/2010-04-01/Accounts/${account_sid}/Calls.json \
  --data-urlencode "ApplicationSid=AP5a83e505ac094ceca073770aacadb825" \
  --data-urlencode "To=${USERPHONE}" \
  --data-urlencode "From=${phone_number}" \
  -u ${account_sid}:${auth_token}

