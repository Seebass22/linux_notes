# copy new files, folders recursively to from source to dest
rsync -avz --ignore-existing source dest

# ignore commonly ignored files and folders, such as .git/
-C
