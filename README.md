echo "This script was written by Dmitry Sorokov from group 710-1"
current_dir=$(pwd)

while true; do
echo "Select action:"
echo "1 - Show current directory"
echo "2 - Go to the directory above"
echo "3 - Go to catalog"
echo "4 - Exit"

read choice

case $choice in
1)
echo "Current directory:$current_dir"
;;
2)
cd ..
current_dir=$(pwd)
echo "Current directory:$current_dir"
;;
3)
echo "Select catalog:"
ls -d */

read dir_choice

if [ -d "$dir_choice" ];
then
cd "$dir_choice"
current_dir=$(pwd)
echo "Current catalog:$current_dir"
else
echo "Directory not found"
fi
;;
4)
echo "Exit from programm"
exit 0
;;
*)
echo "Invalid selection"
;;
esac
done
