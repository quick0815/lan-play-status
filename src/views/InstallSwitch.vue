<template>
  <div class="install">
    <h1>{{ $t("pages.installSwitch.title") }}</h1>
    <InstallConfig
      type="Switch"
      owner="90DNS"
      primary="163.172.141.219"
      secondary="207.246.121.77"
    />
    <p>
      <img
        alt="Settings"
        class="screenshot"
        :src="require(`@/assets/switch/settings1.jpg`)"
      />
    </p>
    <p>
      <img
        alt="Settings"
        class="screenshot"
        :src="require(`@/assets/switch/settings2.jpg`)"
      />
    </p>
    <p>
      <img
        alt="Settings"
        class="screenshot"
        :src="require(`@/assets/switch/settings3.jpg`)"
      />
    </p>
    <Install type="switch" />
    <h2>{{ $t("pages.installSwitch.test.title", { prefix: "4 - " }) }}</h2>
    <p>
      You can test if you have setup everything correctly by putting your Switch
      to sleep and waking it up.
    </p>
    <p>
      If everything is good, you should see (review bold notes in this section)
      <strong>IConnection::IConnection</strong> on your lan-play client. It will
      look like:
    </p>
    <Terminal
      title="user@linux: ~/Downloads"
      content="[DEBUG]: IConnection::IConnection
[DEBUG]: TcpConnection::onConnection
[DEBUG]: ptcp->onConnect
[DEBUG]: lwip->onClose
[DEBUG]: IConnection::writeCallback -89
[DEBUG]: IConnection::~IConnection"
    />
    <p>
      If you do not, verify your switch settings, ensure there is no autoconnect
      profile for a different wireless profile but that autoconnect
      <b>IS</b> enabled for the lanplay profile, and
      <strong>try playing a game</strong>. Failing this, try rebooting your
      switch.
      <strong>
        Failing the internet and/or DNS connectivity test on your switch DOES
        NOT MATTER and can be ignored.
      </strong>
    </p>
    <p>
      <strong>
        Some system combinations no longer show IConnection, but work perfectly
        fine. If you do not see an IConnection, but believe you configured
        everything properly try playing anyway.
      </strong>
    </p>
    <p>
      If you cannot join or create lobbies after asking someone to play with
      you, join #help on the lan-play discord for further assistance. Note: You
      must ask people to play with you or to join others.
    </p>
    <h2>{{ $t("pages.installSwitch.module.title", { prefix: "5 - " }) }}</h2>
    <p>
      You will need to download ldn_mitm if you wish to play to play games that
      don't have the lan play feature (Local Wireless mode Games).
    </p>
    <p>
      You can download the latest ldn_mitm
      <a
        href="https://github.com/spacemeowx2/ldn_mitm/releases"
        target="_blank"
        rel="noreferrer noopener"
      >
        here</a
      >.
    </p>
    <p>
      If you blindly upgraded AMS without checking compatibility, you will need
      to use untested/unsupported nightly builds of ldn_mitm, which are
      <a
        href="https://github.com/spacemeowx2/ldn_mitm/actions"
        target="_blank"
        rel="noreferrer noopener"
      >
        here</a
      >.
    </p>
    <p>
      After you downloaded it extract to the root of your SD card and the module
      should load on your next reboot.
    </p>
    <p>
      After that you just launch your game of choice and select local wireless
      play and you should be good to go.
    </p>
  </div>
</template>

<script>
import InstallConfig from "@/components/InstallConfig.vue";
import Install from "@/components/Install.vue";
import Terminal from "@/components/Terminal.vue";

export default {
  components: {
    InstallConfig,
    Install,
    Terminal
  }
};
</script>
