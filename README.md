aria2seeder
===========

Docker image to easily seed a torrent file.



Usage
-----

    docker run --net=host tomdesinto/aria2seeder http://somewhere.xyz/a_torrent_file.torrent


or if you have a torrent file on your docker host machine:

    docker run --net=host -v /on/my/host/a_torrent_file.torrent:/a_torrent_file.torrent tomdesinto/aria2seeder /a_torrent_file.torrent

    