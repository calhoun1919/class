#!/bin/bash

# 1. Ask for the username
read -p "Enter the username to check: " TARGET_USER

# 2. Check if the user is currently locked
# 'passwd -S' shows status. 'L' indicated locked.
STATUS=$(passwd -S "$TARGET_USER" | awk '{print $2}')

if [[ "$STATUS" =~ L ]]; then
     echo "Account for $TARGET_USER is currently LOCKED!!"

     #3 Ask for confirmation to unlock
     read -p "Would you like to unlock this account (y/n): " CHOICE
     
     if [ "$CHOICE" == "y" ]; then
        passwd -u "$TARGET_USER"
        echo "SUCCESS: $TARGET_USER has been unlocked."
     else
       echo "Action cancelled."
     
     fi
else 
  echo "Account for $TARGET_USER is already UNLOCKED or does not exist."
fi
