FROM nystudio107/webpack-dev-base

WORKDIR /var/www/project/docker-config/webpack-dev-craft/

COPY ./docker-config/webpack-dev-craft/tsconfig.json /var/www/project/tsconfig.json

# Run our webpack build in debug mode

# We'd normally use `npm ci` here, but by using `install`:
# - If `package-lock.json` is present, it will install what is in the lock file
# - If `package-lock.json` is missing, it will update to the latest dependencies
#   and create the `package-lock-json` file
# This automatic running adds to the startup overhead of `docker-compose up`
# but saves far more time in not having to deal with out of sync versions
# when working with teams or multiple environments
CMD npm install \
    && \
    npm run debug
