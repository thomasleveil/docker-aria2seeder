aria2seeder
===========

Docker image to easily seed a torrent file.



Usage
-----

    docker run --net=host tomdesinto/aria2seeder http://somewhere.xyz/a_torrent_file.torrent


or if you have a torrent file on your docker host machine:

    docker run --net=host -v /on/my/host/a_torrent_file.torrent:/a_torrent_file.torrent tomdesinto/aria2seeder /a_torrent_file.torrent

    
The download file(s) will be saved on a volume under the location `/data/` of the container. To access those files, either mount that volume to a directory of your docker host before creating the container: 

    docker run --net=host -v /on/my/host/:/data tomdesinto/aria2seeder http://somewhere.xyz/a_torrent_file.torrent

Of extract the files afterwards with the help of the [`docker cp`](https://docs.docker.com/engine/reference/commandline/cp/) command: 

    docker run --name myseedcontainer --net=host tomdesinto/aria2seeder http://somewhere.xyz/a_torrent_file.torrent  # let's say that this will download a file named foo.zip

    docker cp myseedcontainer:/data/foo.zip .

    
