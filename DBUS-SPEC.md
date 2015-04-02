# DeviceHive GPIO DBus Spec

### Interface com.devicehive.gpio.GpioService
Bus Name: `com.devicehive.gpio`
Path: `/com/devicehive/gpio`

#### Methods:
`list()` - returns list of available gpio pins

`add(pin, port)` - Register pin to expose a physical port

`rm(pin)` - Unregister exposed pin

`clear()` - Unregister all exposed pins

`load_profile(yamlpath)` - Register multiple pins from provided yaml file

`load_profile_for_board(yamldirpath)` - Lookup for the pins yaml file with name from `/sys/firmware/devicetree/base/model` in provided directory. 


#### Introspection:
```xml
<!DOCTYPE node PUBLIC "-//freedesktop//DTD D-BUS Object Introspection 1.0//EN"
"http://www.freedesktop.org/standards/dbus/1.0/introspect.dtd">
<node name="/info">
  <interface name="org.freedesktop.DBus.Introspectable">
    <method name="Introspect">
      <arg direction="out" type="s" />
    </method>
  </interface>
  <interface name="com.devicehive.gpio.GpioService">
    <method name="list">
    </method>
     <method name="load_profile_for_board">
      <arg direction="in"  type="v" name="yamldirpath" />
    </method>
    <method name="clear">
    </method>
    <method name="add">
      <arg direction="in"  type="v" name="pin" />
      <arg direction="in"  type="v" name="port" />
    </method>
    <method name="load_profile">
      <arg direction="in"  type="v" name="yamlpath" />
    </method>
    <method name="rm">
      <arg direction="in"  type="v" name="pin" />
    </method>
  </interface>
</node>
```


### Interface com.devicehive.gpio.GpioPin
Bus Name: `com.devicehive.gpio`
Path: `/com/devicehive/gpio/{PIN}`

#### Methods:
`init(direction)` - initialize pin for input `in` or output `out`

`deinit()` - deinitialize pin and free all resource

`set_value(value)` - set pin state, where value is ether `0` or `1`

`set()` - set pin state to `1`

`clear()` - set pin state to `0`

`get()` - read pin state

`toggle()` - toggle pin state from `0` to `1` or from `1` to `0`


#### Introspection:
```xml
<!DOCTYPE node PUBLIC "-//freedesktop//DTD D-BUS Object Introspection 1.0//EN"
"http://www.freedesktop.org/standards/dbus/1.0/introspect.dtd">
<node name="/info">
  <interface name="org.freedesktop.DBus.Introspectable">
    <method name="Introspect">
      <arg direction="out" type="s" />
    </method>
  </interface>
  <interface name="com.devicehive.gpio.GpioPin">
    <method name="init">
	    <arg direction="in"  type="v" name="mode" />
    </method>
    <method name="deinit">
    </method>
    <method name="set_value">
	    <arg direction="in"  type="v" name="velue" />
    </method>
    <method name="set">
    </method>
    <method name="clear">
    </method>
    <method name="get">
	    <arg direction="out" type="v" />
    </method>
    <method name="toggle">
    </method>
  </interface>
</node>
```

