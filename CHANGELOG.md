## 4.0.0
* Added getting ssl keylog callback for debugging. (#256)
* Fixed re-listen logic for servers. Now we can re-listen after accept is failed. (#252, #254)
* Fixed restore lifetime management to avoid accessing memory after destroyed (#251)
* Removed BOOST_ASSERT checking in the case that actually happens if invalid message is received (#249, #250)
* Added MQTT v5 support (#226, #245, #257, #258, #259)
* Added connection overwrite behavior on `test_broker` (#210)
* Added `async_client` and `sync_client` to avoid misusing async and sync APIs. `client` is still remained that can use both sync and async APIs. (#208)
* Added concatenating `const_buffer` functionality on asynchronous packet sending (#207)
* Improved documents (#198, #214, #219, #229, #235)
* Added switching option between `std` and `boost` (#188, #209)
* Improved build mechanisim (#184, #201, #253)
* Code refactoring (#183, #189, #190, #193, #195, #197, #199, #202, #203, #211, #215, #216, #220, #227, #234, #236, #238, #239, #240, #242)
* Support configure time switches for using std::varient or std::optional instead of the boost versions (#182)
* Allow inheriting classes to construct mqtt::client (#181)
* <<<< Breaking change >> Replaced fixed_header type from `char` to `std::uint8_t`. Fixed `-Wconversion` warnings. See https://github.com/redboltz/mqtt_cpp/pull/180/files (#180)

## 3.1.0
* Fixed inefficient passed by value. (#174)
* Fixed unsugscribe message packet id position for continuours buffer. (#167)
* Fixed subscribe message remaining length buffer size. (#165)
* Added broker example. (#164)
* Improved CI. (#161)
* Added 32bit packet id support. It is out of MQTT spec. (#160, #163, #166, #168)
* Added store assertion to detect internal logic error. (#157)
* Fixed life keeper storing timing. (#156, #159)
* Added getter for handlers. (#155)
* Fixed async write callback. (#154)
* Fixed ambiguous function call on C++17 visit call. (#153)
* Improved packet id allocating algorithm. (#152, #162)
* Removed throwing exception when error on close happens. (#151)
* Added re-listen support after listining socket closed. (#150)
* Fixed string_view definition (#146)
* Added string (UTF-8) checking. It is disabled by default. Define MQTT_USE_STR_CHECK to enable it. (#142, #143)
* Improved documents (#141, #131, #172, #173)
* Improved build mechanisim (#140, #147, #148, #170)
* Added custom next mqtt message read handler setting mechanism (#139)

## 3.0.0
* << Breaking change >> mqtt_cpp requires full C++14 feature.
* Added boost::asio::const_buffer interface. User can use it as topic name and contents(payload).
  (#127, #134, #136)
* Improved CI environment. (#129, #130)
* Fixed packet_id leak. (#132)
* Fixed queuing message leak. (#133)
* Added disconnect timeout. (#135)
* Added connect status check function. (#131)

## 2.1.0
* Added packet length checking handler for variable length MQTT packet. (#121)
* Fixed doxygen comments. (#119)
* Improved payload memory management. (#118)
* Fixed malformed connack (send by client) problem. (#117)
* Fixed missing packet length check on connect. (#116)
* Improved pingreq sending timing. (#115)

## 2.0.0
* << Breaking change >> Updated close_handler and error_handler invoking rule.
  When the socket is closed,
  if user calls disconnect() and the socket closed by server cleanly, then close_handler is called,
  otherwise error_handler is called.
* Added publish and pubrel message serialize mechanism. (#111)
* Added boost beast support. (#106)
* Added boost 1.66.0 asio support. (#106)

## 1.0.9
* Supported Boost 1.66.0 new asio interface. (#106)
* Updated beast to v124. (#107)
* If Boost version is 1.66.0 or later, use Boost.Beast. (#107)
* Improved tests. (#102, #104)
* Improved assetions. (#105)

## 1.0.8
* Added TLS verifying setup functions. (#100)

## 1.0.7
* Update beast. (#94)
* Fixed WebSocket strand management. (#93, #95)
* Fixed endpoint's move constructor and assingment operator deletion (#92)

## 1.0.6
* Update beast. (#90)
* Fixed qos2 publish handler multiple call guard.(#89)

## 1.0.5
* Renamed to `mqtt_cpp` from `mqtt_client_cpp`. (#88)
* Improved tests. (#87)
* Added MQTT server functionality (#84)
* Supressed warnings. (#82)
* Fixed WebSocket close. (#81)
* Added tls context settings. (#80, #83)
* Fixed force_disconnect. (#79)
* Removed TLS manual shutdown call. (#78)
* Fixed timer management algorithm. (#76)
* Fixed pingreq sending timing. (#75)
* Added bad timming mqtt command receiving guard. (#70)

## 1.0.4
* Added offline publish (Clean Session: false, qos: at_least_once, exactly_once). (#69)
* Prepared for OpenSSL 1.1.0 support. (#68)
* Added explicit packet_id acquieing operation. (#67)
* Used C++14 depended code conditionally. (#62, #63)
* Added WebSocket support. (#61, #66)
* Fixed strand. (#60)
* Added strand to shutdown. (#59)
* Fixed the type of qos on async_send_publish. (#58)
* Added async_disconnect function. (#57)
* Fixed async subscribe/unsubscribe. (#56)
* Improved async operations. (#55)
* Fixed SSL_R_SHORT_READ as normal close, not error. (#54)
* Replaced pair with tuple. (#53)
* Fixed endpoint memory management. (#52)

## 1.0.3
* Fixed force disconnect logic. (#50)
* Added remaining length getting function. (#48)
* Added publish with dup flag function. (#47)
* Added for_each function for stored data. (#44)
* Fixed pubrel re-send algorithm. (#43)
* Added pubrel sending interface. (#41)
* Added sent after callback function. (#39)
* Improved CI environment. (#37)
* Improved documents. (#35, #36)
* Removed generic lambda to meet C++11 (#34)
* Added stored packet clearing function. (#32)
* Fixed QoS2 pubrel sending timing.(#31, #46, #49)
* Fixed remaining length handling logic. (#30)
* Added subscribe and unsubscribe with vector. (#29)
* Added suback with vector. (#28)
* Fixed async subscribe bug. (#26)
* Added connect() with socket. (#25)
* Fixed packet_id accqireing algorithm. (#24, #27)
* Fixed storing QoS1 and 2 packet mechanism. (#23)
* Supported async_write operation. (#21)
* Separated MQTT core from client. Core can be used as server connection. (#20)

## 1.0.2
* Fixed queued message clearing problem. (#18)
* Fixed implicit char conversion problem. (#17)
* Fixed missing remaining length checking. (#16)

## 1.0.1
* Updated README.md version number.

## 1.0.0
* Implemented all mqtt functionarities.
