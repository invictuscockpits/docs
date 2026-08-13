# Network Health

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later. On earlier versions, use the warning banner and **Fix** button on the Network page; see [Set Up the Cockpit Network](set-up-the-cockpit-network.md).

Network Health shows every layer of your cockpit network as a row of lights, checked in order from the physical cable up to live board traffic. Open it from the **Network** section of the sidebar with the **Network health** button.

Reading it is simple: **the first red light from the top is where the problem is.** Everything below it usually can't work until that layer is fixed, so start at the top.

If you're working with support, a screenshot of this page answers most of the questions we'd otherwise have to ask one at a time.

---

## The six lights

**1. Network adapter.** A wired network adapter exists and has a live link. Red here means a cable, adapter, or switch-power problem: nothing else can work until a link light is on. USB ethernet adapters count as wired adapters.

**2. Cockpit address.** One of your adapters holds `10.24.6.1`, the address every board calls home to. Red here usually means initial setup hasn't been run on this adapter yet: use **Fix**. A special red case is another device on the network already using the address, which points to the cockpit switch being connected to more than just this PC and your boards.

**3. Cockpit route.** The cockpit address range is pinned to your real adapter, so virtual adapters (Hyper-V, WSL, VPN software) can't intercept board traffic. Yellow means the protection isn't installed yet but nothing is actively conflicting; red means a virtual adapter is sitting on the range right now. **Fix** installs the protection either way.

**4. Windows firewall.** Windows classified the cockpit network as **Private**, which lets boards reach the manager. Red means it's classified **Public**, which silently blocks board connections even when everything else is perfect. **Fix** sets it to Private.

**5. Manager listening.** The manager's board server is running and waiting for connections. This is almost always green; red suggests another program grabbed the manager's port, and a restart of the manager (or the PC) clears it.

**6. Boards connected.** The proof: at least one board has an active connection. If every light above is green but this one is red, the computer side is fine and the problem is on the cockpit side: switch power, PoE (boards power from the switch), the board's cable, or a switch that's connected to your router when it should connect only to this PC and your boards.

This bottom light updates live: when a board connects, it turns green on its own.

---

## The Repair section

**Fix** performs the full first-time network setup on the adapter you pick: assigns the cockpit address, pins the cockpit route, and sets the firewall profile. You'll get one Windows administrator prompt. It's safe to run repeatedly; it only ever repairs, never breaks a working setup.

The adapter dropdown pre-selects our best guess (a wired adapter with a live link). If the chosen adapter also carries your internet connection, a caution appears: a dedicated cockpit adapter is the recommended setup, and a USB ethernet adapter is an inexpensive way to add one. See [Set Up the Cockpit Network](set-up-the-cockpit-network.md) for single-port options.

---

**See also:** [Set Up the Cockpit Network](set-up-the-cockpit-network.md), [Troubleshooting](troubleshooting.md), [Add Your First Board](add-your-first-board.md)
