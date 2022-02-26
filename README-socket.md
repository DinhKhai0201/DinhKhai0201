# Kai1997

### sending to sender-client only
socket.emit('message', "this is a message");

### sending to all clients, include sender
io.emit('message', "this is a message");

### sending to all clients except sender
socket.broadcast.emit('message', "this is a message");

### sending to all clients in 'anime' room(channel) except sender
socket.broadcast.to('anime').emit('message', 'nice anime');

### sending to all clients in 'anime' room(channel), include sender
io.in('anime').emit('message', 'nice anime');

### sending to sender client, only if they are in 'anime' room(channel)
socket.to('anime').emit('message', 'join the anime');

### sending to all clients in namespace 'myNamespace', include sender
io.of('myNamespace').emit('message', 'gg');

### sending to individual socketid
socket.broadcast.to(socketid).emit('message', ' send to a user');

### list socketid
for (var socketid in io.sockets.sockets) {}
 OR
Object.keys(io.sockets.sockets).forEach((socketid) => {});
