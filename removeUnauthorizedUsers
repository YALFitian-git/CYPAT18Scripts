readarray -t userList< <(cut -d: -f1 /etc/passwd) 
readarray -t adminList< <(getent group sudo) 
echo "Paste in the authorized users list from the README." 
read authUsers 
suspUsers="${userList/$authUsers/}" 
if [[ -z "${suspUsers[@]}" ]]; then 
echo "No suspicious users were found." 
exit 
else 
echo "Suspicious users found: $suspUsers. Remove them? (Y/N)" 
fi 
