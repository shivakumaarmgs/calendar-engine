## Demo For Calendar Engine

Fullcalendar engine is mounted at `/calendar` path

Events are getting saved
```
Started POST "/calendar/events" for 127.0.0.1 at 2014-05-05 10:20:22 +0530
Processing by FullcalendarEngine::EventsController#create as */*
  Parameters: {"utf8"=>"✓", "authenticity_token"=>"M/LBlEtTnnAXRqYgwxr6NFssohMFPxl0tpjI7ewBJLI=", "event"=>{"title"=>"Eventone one", "description"=>"one", "starttime(1i)"=>"2014", "starttime(2i)"=>"5", "starttime(3i)"=>"6", "starttime(4i)"=>"06", "starttime(5i)"=>"15", "endtime(1i)"=>"2014", "endtime(2i)"=>"5", "endtime(3i)"=>"6", "endtime(4i)"=>"06", "endtime(5i)"=>"30", "all_day"=>"0", "period"=>"Does not repeat", "frequency"=>"1"}}
   (0.1ms)  begin transaction
  SQL (0.5ms)  INSERT INTO "fullcalendar_engine_events" ("created_at", "description", "endtime", "starttime", "title", "updated_at") VALUES (?, ?, ?, ?, ?, ?)  [["created_at", "2014-05-05 04:50:22.905410"], ["description", "one"], ["endtime", "2014-05-06 06:30:00.000000"], ["starttime", "2014-05-06 06:15:00.000000"], ["title", "Eventone one"], ["updated_at", "2014-05-05 04:50:22.905410"]]
   (130.8ms)  commit transaction
  Rendered text template (0.0ms)
Completed 200 OK in 140ms (Views: 0.7ms | ActiveRecord: 131.4ms)
```

But not displayed
```
Started GET "/events/get_events?start=1399141800&end=1399746600&_=1399265367616" for 127.0.0.1 at 2014-05-05 10:20:23 +0530

ActionController::RoutingError (No route matches [GET] "/events/get_events"):
  actionpack (4.1.0) lib/action_dispatch/middleware/debug_exceptions.rb:21:in `call'
  actionpack (4.1.0) lib/action_dispatch/middleware/show_exceptions.rb:30:in `call'
  railties (4.1.0) lib/rails/rack/logger.rb:38:in `call_app'
  railties (4.1.0) lib/rails/rack/logger.rb:20:in `block in call'
  activesupport (4.1.0) lib/active_support/tagged_logging.rb:68:in `block in tagged'
  activesupport (4.1.0) lib/active_support/tagged_logging.rb:26:in `tagged'
  activesupport (4.1.0) lib/active_support/tagged_logging.rb:68:in `tagged'
  railties (4.1.0) lib/rails/rack/logger.rb:20:in `call'
  actionpack (4.1.0) lib/action_dispatch/middleware/request_id.rb:21:in `call'
  rack (1.5.2) lib/rack/methodoverride.rb:21:in `call'
  rack (1.5.2) lib/rack/runtime.rb:17:in `call'
  activesupport (4.1.0) lib/active_support/cache/strategy/local_cache_middleware.rb:26:in `call'
  rack (1.5.2) lib/rack/lock.rb:17:in `call'
  actionpack (4.1.0) lib/action_dispatch/middleware/static.rb:64:in `call'
  rack (1.5.2) lib/rack/sendfile.rb:112:in `call'
  railties (4.1.0) lib/rails/engine.rb:514:in `call'
  railties (4.1.0) lib/rails/application.rb:144:in `call'
  rack (1.5.2) lib/rack/lock.rb:17:in `call'
  rack (1.5.2) lib/rack/content_length.rb:14:in `call'
  rack (1.5.2) lib/rack/handler/webrick.rb:60:in `service'
  /home/shivakumaarmgs/.rvm/rubies/ruby-2.1.1/lib/ruby/2.1.0/webrick/httpserver.rb:138:in `service'
  /home/shivakumaarmgs/.rvm/rubies/ruby-2.1.1/lib/ruby/2.1.0/webrick/httpserver.rb:94:in `run'
  /home/shivakumaarmgs/.rvm/rubies/ruby-2.1.1/lib/ruby/2.1.0/webrick/server.rb:295:in `block in start_thread'
  ```
