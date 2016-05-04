
  default: &default
    adapter: postgresql
    encoding: unicode
    # For details on connection pooling, see rails configuration guide
    # http://guides.rubyonrails.org/configuring.html#database-pooling
    pool: 5

  development:
    <<: *default
    database: app_pg_development
    
  test:
    <<: *default
    database: app_pg_test

  production:
    <<: *default
    database: app_pg_production
    username: app_pg
    password: <%= ENV['APP_PG_DATABASE_PASSWORD'] %>
