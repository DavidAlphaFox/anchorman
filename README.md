# Anchorman
> 60% of the time, it works every time

## Architecture (Explained Shell Session)

```erlang
1> application:start(anchorman).
% the anchorman_app will start up the anchorman_sup
% the anchorman_sup will start the anchorman_server
% the server will then sit idle awaiting for messages
ok
2> anchorman:listen(Event, fun Cb/1).
% the callback function will be added to the list of listeners for that event
3> anchorman:publish(Event, Data).
% Cb will be called with Data
```
