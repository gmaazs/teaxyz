## Bone - 0.2 ##

**Bones it!**

## Features

* Store variables and files remotely
* Simple interface

## CLI Example
    
    # Specify arbitrary keys and values. 
    $ bone set cust_id c397d204aa4e94f566d7f78c
    $ bone cust_id
    c397d204aa4e94f566d7f78c
    
    # File contents are read automatically...
    $ bone set redis_conf config/redis-server.conf
    $ bone redis_conf 
    # Redis configuration file example
    ...
    
    # unless you specify -s
    $ bone set -s redis_conf config/redis-server.conf
    $ bone redis_conf
    config/redis-server.conf
    
    # Show all available keys
    $ bone keys
    
    
## Ruby Example

    require 'bone'
    
    ENV['BONE_TOKEN'] = Bone.generate_token
    
    Bone[:cust_id] = 'c397d204aa4e94f566d7f78c'
    Bone[:redis_conf] = File.read('config/redis-server.conf')
    
    Bone[:cust_id]                    # => "c397d204aa4e94f566d7f78c"
    Bone[:redis_conf]                 # => "# Redis configuration file example..."
    
    
## Installation

    $ sudo gem install bone
    $ bone token
    $ export BONE_TOKEN=YOURTOKEN
    
You also need to running instance of [boned](http://github.com/solutious/boned) (the bone daemon).

    
## More Information


## Credits

* Delano Mandelbaum (http://solutious.com)


## Thanks 

* Kalin Harvey for the early feedback. 


## License

See LICENSE.txt