cmake_minimum_required(VERSION 3.15)
project(logcabin)

set(CMAKE_CXX_STANDARD 14)

include_directories(Client)
include_directories(Core)
include_directories(Event)
include_directories(gtest/include)
include_directories(gtest/include/gtest)
include_directories(gtest/include/gtest/internal)
include_directories(gtest/samples)
include_directories(gtest/src)
include_directories(gtest/test)
include_directories(gtest/xcode/Samples/FrameworkSample)
include_directories(include)
include_directories(include/LogCabin)
include_directories(Protocol)
include_directories(RPC)
include_directories(Server)
include_directories(Storage)
include_directories(Tree)

include_directories(build)

add_executable(logcabin
        Client/Backoff.cc
        Client/Backoff.h
        Client/BackoffTest.cc
        Client/Client.cc
        Client/ClientImpl.cc
        Client/ClientImpl.h
        Client/ClientImplTest.cc
        Client/ClientTest.cc
        Client/LeaderRPC.cc
        Client/LeaderRPC.h
        Client/LeaderRPCMock.cc
        Client/LeaderRPCMock.h
        Client/LeaderRPCTest.cc
        Client/MockClientImpl.cc
        Client/MockClientImpl.h
        Client/MockClientImplTest.cc
        Client/ServerControl.cc
        Client/SessionManager.cc
        Client/SessionManager.h
        Client/SessionManagerTest.cc
        Client/Util.cc
        Client/UtilTest.cc
        Core/Buffer.cc
        Core/Buffer.h
        Core/BufferTest.cc
        Core/Checksum.cc
        Core/Checksum.h
        Core/ChecksumTest.cc
        Core/CompatAtomic.h
        Core/CompatHash.h
        Core/CompatHashTest.cc
        Core/ConditionVariable.cc
        Core/ConditionVariable.h
        Core/ConditionVariableTest.cc
        Core/Config.cc
        Core/Config.h
        Core/ConfigTest.cc
        Core/Debug.cc
        Core/Debug.h
        Core/DebugTest.cc
        Core/Endian.h
        Core/Mutex.h
        Core/ProtoBuf.cc
        Core/ProtoBuf.h
        Core/ProtoBufTest.cc
        Core/Random.cc
        Core/Random.h
        Core/RandomTest.cc
        Core/RollingStat.cc
        Core/RollingStat.h
        Core/RollingStatTest.cc
        Core/STLUtil.h
        Core/STLUtilTest.cc
        Core/StringUtil.cc
        Core/StringUtil.h
        Core/StringUtilTest.cc
        Core/ThreadId.cc
        Core/ThreadId.h
        Core/ThreadIdTest.cc
        Core/Time.cc
        Core/Time.h
        Core/TimeTest.cc
        Core/Util.cc
        Core/Util.h
        Core/UtilTest.cc
        Event/File.cc
        Event/File.h
        Event/FileTest.cc
        Event/Loop.cc
        Event/Loop.h
        Event/LoopTest.cc
        Event/Signal.cc
        Event/Signal.h
        Event/SignalTest.cc
        Event/Timer.cc
        Event/Timer.h
        Event/TimerTest.cc
        Examples/Benchmark.cc
        Examples/FailoverTest.cc
        Examples/HelloWorld.cc
        Examples/Reconfigure.cc
        Examples/ReconfigureTest.cc
        Examples/SmokeTest.cc
        Examples/TreeOps.cc
        gtest/codegear/gtest_all.cc
        gtest/codegear/gtest_link.cc
        gtest/include/gtest/internal/gtest-death-test-internal.h
        gtest/include/gtest/internal/gtest-filepath.h
        gtest/include/gtest/internal/gtest-internal.h
        gtest/include/gtest/internal/gtest-linked_ptr.h
        gtest/include/gtest/internal/gtest-param-util-generated.h
        gtest/include/gtest/internal/gtest-param-util.h
        gtest/include/gtest/internal/gtest-port.h
        gtest/include/gtest/internal/gtest-string.h
        gtest/include/gtest/internal/gtest-tuple.h
        gtest/include/gtest/internal/gtest-type-util.h
        gtest/include/gtest/gtest-death-test.h
        gtest/include/gtest/gtest-message.h
        gtest/include/gtest/gtest-param-test.h
        gtest/include/gtest/gtest-printers.h
        gtest/include/gtest/gtest-spi.h
        gtest/include/gtest/gtest-test-part.h
        gtest/include/gtest/gtest-typed-test.h
        gtest/include/gtest/gtest.h
        gtest/include/gtest/gtest_pred_impl.h
        gtest/include/gtest/gtest_prod.h
        gtest/samples/prime_tables.h
        gtest/samples/sample1.cc
        gtest/samples/sample1.h
        gtest/samples/sample10_unittest.cc
        gtest/samples/sample1_unittest.cc
        gtest/samples/sample2.cc
        gtest/samples/sample2.h
        gtest/samples/sample2_unittest.cc
        gtest/samples/sample3-inl.h
        gtest/samples/sample3_unittest.cc
        gtest/samples/sample4.cc
        gtest/samples/sample4.h
        gtest/samples/sample4_unittest.cc
        gtest/samples/sample5_unittest.cc
        gtest/samples/sample6_unittest.cc
        gtest/samples/sample7_unittest.cc
        gtest/samples/sample8_unittest.cc
        gtest/samples/sample9_unittest.cc
        gtest/src/gtest-all.cc
        gtest/src/gtest-death-test.cc
        gtest/src/gtest-filepath.cc
        gtest/src/gtest-internal-inl.h
        gtest/src/gtest-port.cc
        gtest/src/gtest-printers.cc
        gtest/src/gtest-test-part.cc
        gtest/src/gtest-typed-test.cc
        gtest/src/gtest.cc
        gtest/src/gtest_main.cc
        gtest/test/gtest-death-test_ex_test.cc
        gtest/test/gtest-death-test_test.cc
        gtest/test/gtest-filepath_test.cc
        gtest/test/gtest-linked_ptr_test.cc
        gtest/test/gtest-listener_test.cc
        gtest/test/gtest-message_test.cc
        gtest/test/gtest-options_test.cc
        gtest/test/gtest-param-test2_test.cc
        gtest/test/gtest-param-test_test.cc
        gtest/test/gtest-param-test_test.h
        gtest/test/gtest-port_test.cc
        gtest/test/gtest-printers_test.cc
        gtest/test/gtest-test-part_test.cc
        gtest/test/gtest-tuple_test.cc
        gtest/test/gtest-typed-test2_test.cc
        gtest/test/gtest-typed-test_test.cc
        gtest/test/gtest-typed-test_test.h
        gtest/test/gtest-unittest-api_test.cc
        gtest/test/gtest_all_test.cc
        gtest/test/gtest_break_on_failure_unittest_.cc
        gtest/test/gtest_catch_exceptions_test_.cc
        gtest/test/gtest_color_test_.cc
        gtest/test/gtest_env_var_test_.cc
        gtest/test/gtest_environment_test.cc
        gtest/test/gtest_filter_unittest_.cc
        gtest/test/gtest_help_test_.cc
        gtest/test/gtest_list_tests_unittest_.cc
        gtest/test/gtest_main_unittest.cc
        gtest/test/gtest_nc.cc
        gtest/test/gtest_no_test_unittest.cc
        gtest/test/gtest_output_test_.cc
        gtest/test/gtest_pred_impl_unittest.cc
        gtest/test/gtest_prod_test.cc
        gtest/test/gtest_repeat_test.cc
        gtest/test/gtest_shuffle_test_.cc
        gtest/test/gtest_sole_header_test.cc
        gtest/test/gtest_stress_test.cc
        gtest/test/gtest_throw_on_failure_ex_test.cc
        gtest/test/gtest_throw_on_failure_test_.cc
        gtest/test/gtest_uninitialized_test_.cc
        gtest/test/gtest_unittest.cc
        gtest/test/gtest_xml_outfile1_test_.cc
        gtest/test/gtest_xml_outfile2_test_.cc
        gtest/test/gtest_xml_output_unittest_.cc
        gtest/test/production.cc
        gtest/test/production.h
        gtest/xcode/Samples/FrameworkSample/widget.cc
        gtest/xcode/Samples/FrameworkSample/widget.h
        gtest/xcode/Samples/FrameworkSample/widget_test.cc
        include/LogCabin/Client.h
        include/LogCabin/Debug.h
        include/LogCabin/Util.h
        Protocol/Common.h
        RPC/Address.cc
        RPC/Address.h
        RPC/AddressTest.cc
        RPC/ClientRPC.cc
        RPC/ClientRPC.h
        RPC/ClientRPCTest.cc
        RPC/ClientServerTest.cc
        RPC/ClientSession.cc
        RPC/ClientSession.h
        RPC/ClientSessionTest.cc
        RPC/MessageSocket.cc
        RPC/MessageSocket.h
        RPC/MessageSocketTest.cc
        RPC/OpaqueClientRPC.cc
        RPC/OpaqueClientRPC.h
        RPC/OpaqueClientRPCTest.cc
        RPC/OpaqueServer.cc
        RPC/OpaqueServer.h
        RPC/OpaqueServerRPC.cc
        RPC/OpaqueServerRPC.h
        RPC/OpaqueServerRPCTest.cc
        RPC/OpaqueServerTest.cc
        RPC/Protocol.cc
        RPC/Protocol.h
        RPC/Server.cc
        RPC/Server.h
        RPC/ServerRPC.cc
        RPC/ServerRPC.h
        RPC/ServerRPCTest.cc
        RPC/ServerTest.cc
        RPC/Service.h
        RPC/ServiceMock.cc
        RPC/ServiceMock.h
        RPC/ThreadDispatchService.cc
        RPC/ThreadDispatchService.h
        RPC/ThreadDispatchServiceTest.cc
        Server/ClientService.cc
        Server/ClientService.h
        Server/ClientServiceTest.cc
        Server/ControlService.cc
        Server/ControlService.h
        Server/Globals.cc
        Server/Globals.h
        Server/GlobalsTest.cc
        Server/Main.cc
        Server/RaftConsensus.cc
        Server/RaftConsensus.h
        Server/RaftConsensusInvariants.cc
        Server/RaftConsensusTest.cc
        Server/RaftService.cc
        Server/RaftService.h
        Server/ServerStats.cc
        Server/ServerStats.h
        Server/ServerStatsTest.cc
        Server/StateMachine.cc
        Server/StateMachine.h
        Server/StateMachineTest.cc
        Storage/FilesystemUtil.cc
        Storage/FilesystemUtil.h
        Storage/FilesystemUtilTest.cc
        Storage/Layout.cc
        Storage/Layout.h
        Storage/LayoutTest.cc
        Storage/Log.cc
        Storage/Log.h
        Storage/LogFactory.cc
        Storage/LogFactory.h
        Storage/LogFactoryTest.cc
        Storage/MemoryLog.cc
        Storage/MemoryLog.h
        Storage/MemoryLogTest.cc
        Storage/SegmentedLog.cc
        Storage/SegmentedLog.h
        Storage/SegmentedLogTest.cc
        Storage/SimpleFileLog.cc
        Storage/SimpleFileLog.h
        Storage/SimpleFileLogTest.cc
        Storage/SnapshotFile.cc
        Storage/SnapshotFile.h
        Storage/SnapshotFileTest.cc
        Storage/Tool.cc
        test/TestRunner.cc
        Tree/ProtoBuf.cc
        Tree/ProtoBuf.h
        Tree/ProtoBufTest.cc
        Tree/Tree.cc
        Tree/Tree.h
        Tree/TreeTest.cc

        build/Client/Backoff.cc
        build/Client/Backoff.h
        build/Client/BackoffTest.cc
        build/Client/Client.cc
        build/Client/ClientImpl.cc
        build/Client/ClientImpl.h
        build/Client/ClientImplTest.cc
        build/Client/ClientTest.cc
        build/Client/LeaderRPC.cc
        build/Client/LeaderRPC.h
        build/Client/LeaderRPCMock.cc
        build/Client/LeaderRPCMock.h
        build/Client/LeaderRPCTest.cc
        build/Client/MockClientImpl.cc
        build/Client/MockClientImpl.h
        build/Client/MockClientImplTest.cc
        build/Client/ServerControl.cc
        build/Client/SessionManager.cc
        build/Client/SessionManager.h
        build/Client/SessionManagerTest.cc
        build/Client/Util.cc
        build/Client/UtilTest.cc
        build/Core/Buffer.cc
        build/Core/Buffer.h
        build/Core/BufferTest.cc
        build/Core/Checksum.cc
        build/Core/Checksum.h
        build/Core/ChecksumTest.cc
        build/Core/CompatAtomic.h
        build/Core/CompatHash.h
        build/Core/CompatHashTest.cc
        build/Core/ConditionVariable.cc
        build/Core/ConditionVariable.h
        build/Core/ConditionVariableTest.cc
        build/Core/Config.cc
        build/Core/Config.h
        build/Core/ConfigTest.cc
        build/Core/Debug.cc
        build/Core/Debug.h
        build/Core/DebugTest.cc
        build/Core/Endian.h
        build/Core/Mutex.h
        build/Core/ProtoBuf.cc
        build/Core/ProtoBuf.h
        build/Core/ProtoBufTest.cc
        build/Core/Random.cc
        build/Core/Random.h
        build/Core/RandomTest.cc
        build/Core/RollingStat.cc
        build/Core/RollingStat.h
        build/Core/RollingStatTest.cc
        build/Core/STLUtil.h
        build/Core/STLUtilTest.cc
        build/Core/StringUtil.cc
        build/Core/StringUtil.h
        build/Core/StringUtilTest.cc
        build/Core/ThreadId.cc
        build/Core/ThreadId.h
        build/Core/ThreadIdTest.cc
        build/Core/Time.cc
        build/Core/Time.h
        build/Core/TimeTest.cc
        build/Core/Util.cc
        build/Core/Util.h
        build/Core/UtilTest.cc
        build/Event/File.cc
        build/Event/File.h
        build/Event/FileTest.cc
        build/Event/Loop.cc
        build/Event/Loop.h
        build/Event/LoopTest.cc
        build/Event/Signal.cc
        build/Event/Signal.h
        build/Event/SignalTest.cc
        build/Event/Timer.cc
        build/Event/Timer.h
        build/Event/TimerTest.cc
        build/Examples/Benchmark.cc
        build/Examples/FailoverTest.cc
        build/Examples/HelloWorld.cc
        build/Examples/Reconfigure.cc
        build/Examples/ReconfigureTest.cc
        build/Examples/SmokeTest.cc
        build/Examples/TreeOps.cc

        build/Protocol/Common.h
        build/RPC/Address.cc
        build/RPC/Address.h
        build/RPC/AddressTest.cc
        build/RPC/ClientRPC.cc
        build/RPC/ClientRPC.h
        build/RPC/ClientRPCTest.cc
        build/RPC/ClientServerTest.cc
        build/RPC/ClientSession.cc
        build/RPC/ClientSession.h
        build/RPC/ClientSessionTest.cc
        build/RPC/MessageSocket.cc
        build/RPC/MessageSocket.h
        build/RPC/MessageSocketTest.cc
        build/RPC/OpaqueClientRPC.cc
        build/RPC/OpaqueClientRPC.h
        build/RPC/OpaqueClientRPCTest.cc
        build/RPC/OpaqueServer.cc
        build/RPC/OpaqueServer.h
        build/RPC/OpaqueServerRPC.cc
        build/RPC/OpaqueServerRPC.h
        build/RPC/OpaqueServerRPCTest.cc
        build/RPC/OpaqueServerTest.cc
        build/RPC/Protocol.cc
        build/RPC/Protocol.h
        build/RPC/Server.cc
        build/RPC/Server.h
        build/RPC/ServerRPC.cc
        build/RPC/ServerRPC.h
        build/RPC/ServerRPCTest.cc
        build/RPC/ServerTest.cc
        build/RPC/Service.h
        build/RPC/ServiceMock.cc
        build/RPC/ServiceMock.h
        build/RPC/ThreadDispatchService.cc
        build/RPC/ThreadDispatchService.h
        build/RPC/ThreadDispatchServiceTest.cc
        build/Server/ClientService.cc
        build/Server/ClientService.h
        build/Server/ClientServiceTest.cc
        build/Server/ControlService.cc
        build/Server/ControlService.h
        build/Server/Globals.cc
        build/Server/Globals.h
        build/Server/GlobalsTest.cc
        build/Server/Main.cc
        build/Server/RaftConsensus.cc
        build/Server/RaftConsensus.h
        build/Server/RaftConsensusInvariants.cc
        build/Server/RaftConsensusTest.cc
        build/Server/RaftService.cc
        build/Server/RaftService.h
        build/Server/ServerStats.cc
        build/Server/ServerStats.h
        build/Server/ServerStatsTest.cc
        build/Server/StateMachine.cc
        build/Server/StateMachine.h
        build/Server/StateMachineTest.cc
        build/Storage/FilesystemUtil.cc
        build/Storage/FilesystemUtil.h
        build/Storage/FilesystemUtilTest.cc
        build/Storage/Layout.cc
        build/Storage/Layout.h
        build/Storage/LayoutTest.cc
        build/Storage/Log.cc
        build/Storage/Log.h
        build/Storage/LogFactory.cc
        build/Storage/LogFactory.h
        build/Storage/LogFactoryTest.cc
        build/Storage/MemoryLog.cc
        build/Storage/MemoryLog.h
        build/Storage/MemoryLogTest.cc
        build/Storage/SegmentedLog.cc
        build/Storage/SegmentedLog.h
        build/Storage/SegmentedLogTest.cc
        build/Storage/SimpleFileLog.cc
        build/Storage/SimpleFileLog.h
        build/Storage/SimpleFileLogTest.cc
        build/Storage/SnapshotFile.cc
        build/Storage/SnapshotFile.h
        build/Storage/SnapshotFileTest.cc
        build/Storage/Tool.cc
        build/test/TestRunner.cc
        build/Tree/ProtoBuf.cc
        build/Tree/ProtoBuf.h
        build/Tree/ProtoBufTest.cc
        build/Tree/Tree.cc
        build/Tree/Tree.h
        build/Tree/TreeTest.cc

        )
