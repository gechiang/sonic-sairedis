AM_CFLAGS = $(SAIINC)
AM_CXXFLAGS = $(SAIINC) -I$(top_srcdir)/lib

lib_LTLIBRARIES = libsaimetadata.la libsaimeta.la

BUILT_SOURCES = $(top_srcdir)/SAI/meta/saimetadata.c $(top_srcdir)/SAI/meta/saimetadata.h

$(top_srcdir)/SAI/meta/saimetadata.c $(top_srcdir)/SAI/meta/saimetadata.h: saimeta-gen

saimeta-gen:
	make -C $(top_srcdir)/SAI/meta saimetadata.c

clean-local:
	make -C $(top_srcdir)/SAI/meta clean

libsaimetadata_la_SOURCES =  \
				$(top_srcdir)/SAI/meta/saimetadata.c \
				$(top_srcdir)/SAI/meta/saimetadatautils.c \
				$(top_srcdir)/SAI/meta/saiserialize.c

libsaimetadata_la_CPPFLAGS = $(CODE_COVERAGE_CPPFLAGS)
libsaimetadata_la_CFLAGS = $(DBGFLAGS) $(AM_CFLAGS) -ansi $(CODE_COVERAGE_CFLAGS)

libsaimeta_la_SOURCES = \
				AttrKeyMap.cpp \
				Globals.cpp \
				Meta.cpp \
				MetaKeyHasher.cpp \
				Notification.cpp \
				NotificationFactory.cpp \
				NotificationFdbEvent.cpp \
				NotificationPortStateChange.cpp \
				NotificationQueuePfcDeadlock.cpp \
				NotificationSwitchShutdownRequest.cpp \
				NotificationSwitchStateChange.cpp \
				NotificationBfdSessionStateChange.cpp \
				NumberOidIndexGenerator.cpp \
				OidRefCounter.cpp \
				PerformanceIntervalTimer.cpp \
				PortRelatedSet.cpp \
				RedisSelectableChannel.cpp \
				SaiAttrWrapper.cpp \
				SaiAttributeList.cpp \
				SaiInterface.cpp \
				SaiObject.cpp \
				SaiObjectCollection.cpp \
				SaiSerialize.cpp \
				SelectableChannel.cpp \
				ZeroMQSelectableChannel.cpp

libsaimeta_la_CPPFLAGS = $(CODE_COVERAGE_CPPFLAGS)
libsaimeta_la_CXXFLAGS = $(DBGFLAGS) $(AM_CXXFLAGS) $(CXXFLAGS_COMMON) $(CODE_COVERAGE_CXXFLAGS)
libsaimeta_la_LIBADD = -lhiredis -lswsscommon libsaimetadata.la $(CODE_COVERAGE_LIBS)
