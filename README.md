# `forgottenserver` development environment

1. Clone this repository.

2. Clone the `forgottenserver` repository inside this repository.

3. Run `docker-compose up` to start the development environment.

4. Go to `http://localhost:8080` to access the phpMyAdmin. Use the following
credentials to login: `root:root`.

5. Import `apache/ZnoteAAC-1.6/engine/database/znote_schema.sql` into the
`forgottenserver` database.

6. Go to `http://localhost` to access the `forgottenserver` website and create
an account.

7. Compile the `forgottenserver` (e.g.,
`cmake -Bbuild -GNinja -DCMAKE_BUILD_TYPE=RelWithDebInfo -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -DSKIP_GIT=ON && ninja -C build`).

8. Copy and paste the `config.lua.dist` file to `config.lua` and add the
following lines to the end of the file:

```lua
mysqlHost = "127.0.0.1"
mysqlUser = "root"
mysqlPass = "root"
mysqlDatabase = "forgottenserver"
mysqlPort = 3306
```

9. Run the `forgottenserver`.

10. Develop and have fun!
