# Lygos

Lygos is a visual data analytics software for video walls and dashboards used in Control Rooms, Operation Centers and Office Dashboards. It enables users to deploy collages of interactive, realtime data visualizations and maps scaled to 100+ million pixels seamless screen areas on distributed screen clients. It can be collaboratively controlled through clients on computers and tablets.  

This Repo contains latest Windows, Linux and Mac Releases of Lygos

Please visit [Lygos Website](https://lygos.io) for more information about lygos software.

Please visit [Lygos Release Notes](https://lygosio.atlassian.net/wiki/external/ZDg2YTQ0NDY0MjAzNGY2OGJhZTI4ZTI1ZjlkMWQxZmM)

IMPORTANT! By downloading our software you will be accepting our [EULA](https://lygos.io/eula)!

# Installation and Setup

For Version v.4.0.0

## Prerequisites and System Requirements

Before beginning installation ensure your environment meets the following requirements.

### Hardware Recommendations

Below table shows hardware requirements for PCs used as Screen Node, Server, Management or Control Clients.

| **Mode**        | **GPU**   | **CPU**        | **Memory**    | **Network** |
| --------------- | --------- | -------------- | ------------- | ----------- |
| Single Client   | High      | Medium (i5)    | Low (8GB)     | 100 Megabit |
| Multi-Client    | Very High | High (i7)      | Medium (16GB) | Gigabit     |
| Only Server     | Low       | High (i7)      | Medium (16GB) | Gigabit     |
| Server & Client | High      | Very High (i9) | High (32GB)   | Gigabit     |

Multiple client windows can be summoned on each computer. The total resolution of these windows determine the actual requirement of that device.

### Considerations and Suggestions

**Use identical hardware for screen clients:** Promotes better temporal and visual synchronization across video walls.

**Dedicated Server PC:** Avoid using the server PC for screens or control clients to prevent resource contention and control issues.

**High-End Server Device:** Should have strong CPU/GPU/network, minimal background processes, and run on a gigabit LAN.

If the server is also used as a screen client, turning off a screen might inadvertently turn off the server. Best to separate server from screen roles.

## Setup Modes

Lygos offers a highly flexible architecture to support various hardware and space configurations. At its core:

- One PC instance must run as the Server (Local Mode).
- That server can summon Screen, Management, and Control Clients.
- Other PC/Tablet instances can connect to this server and summon Screen, Management, and Control Clients.

Even though you can create any setup with Lygos, here are some common ones as examples:

### Large TV Mode

![](https://lygos.io/images/docs/setup/setupModes_setup-modes-1.svg)

- Acts as a single screenspace.
- Multiple Maps, Visualizations, or Media elements can be deployed to its grid layout.
- The screen client typically runs on the PC that runs on server mode.
- Touchscreen or secondary displays on the server can run Control or Management Clients.
- Remote PCs and tablets can connect as additional control interfaces.

**Best suited for:**

- Small setups
- Professional data presentations
- Single dashboards

### Video Wall Mode

Multi-screen display acting as a unified seamless screenspace

![](https://lygos.io/images/docs/setup/setupModes_setup-modes-2.svg)

There are several general options for how you can [set up your video wall:](https://lygos.io/docs/setup/setup-modes)

- Example Option 1:
  - Setup: Each video wall display can be connected to a **separate PC**
  - Installation: Lygos runs on each PC, summoning a single screen client
  - Resolution: Full
  - Processing Power Requirement: Low
  - Synchronization: Required
- Example Option 2:
  - Setup: One **PC per row** of displays
  - Installation: Lygos runs on each PC, summoning multiple screen clients for each monitor
  - Resolution: Full
  - Processing Power Requirement: Medium
  - Synchronization: Required
- Example Option 3:
  - Setup: A **single PC** driving a **small video wall** (Each display is connected to PC separately)
  - Installation: Lygos summons a single screen client for whole videowall (Maximum 4 Displays)
  - Resolution: Full
  - Processing Power Requirement: Medium
  - Synchronization: Not Required
- Example Option 4:
  - Setup: A **single PC** driving a **small video wall** (Videowall connected from single connector)
  - Installation: Lygos summons a single screen client for whole videowall
  - Resolution: Limited (Videowall itself reduced its resolution to serve from a single connector)
  - Processing Power Requirement: Medium
  - Synchronization: Not Required
- Example Option 5:
  - Setup: A **specialized PC or hardware equipment** that connects to a large videowall and treat it as a single high-resolution screen
  - Installation: Lygos summons a single screen client for whole video wall
  - Resolution: Full
  - Processing Power Requirement: Very High
  - Synchronization: Not Required

**Warning Regarding Option 5:**

Lygos screens will not be distributed and operate on a single screen client with full resolution of the videowall, thus rendering thousands, maybe millions of UI

elements depending on how many displays on the videowall.

First of all, this requires very high GPU and CPU power.

Furthermore, regardless of PC or equipment providing this required processing power on a single device, it may still crash or lag due to limitations of operating system and drivers for displaying large number of elements at such high resolution on a single window.

Usually, software, including the various third party graphic or UI packages Lygos use, are designed for normal resolutions: up to 4K. Therefore, Lygos prefer distribution of screens, where each screen render no more than 1-8K and render only partial amount of UI elements, rather than displaying such resolutions with ultra high number of UI elements on a single window.

Screen clients can synchronize in **<100ms** for seamless map,

visualization and media render and control on seamless screen space made of distributed screen client nodes.

A **single lygos screen client** can span up to **4 adjacent identical monitors**. This is used for having a single screen client for small video walls. This removes

requirement of synchronization on a small videowall, improving video

synchronization performance that span to multiple displays. You can access span options through window control menu on top right of a screen client summoned on a PC Version of the software

**Example Use Cases:**

- Control Centers
- Command Centers
- Operation Centers
- Digital Art Installations
- Open Offices
- Conference Rooms

### Signage/Dashboard Mode

Multiple independent screenspaces (of same or different sizes/configs) can connect to a single Lygos server.

![](https://lygos.io/images/docs/setup/setupModes_setup-modes-3.svg)
For example, you can use multiple regular TVs in an office space as dashboards which can be controlled by selected few, or have multiple conference rooms each with its video wall or large TV or have few displays at office corridors as signage looping through content.

Each of these screenspaces can access the same visualization resources on the server.

This setup can be in addition to your main video wall setup since Lygos provides flexibility on connecting multiple screenspaces and displaying separate layouts on each screenspace.

**Example Use Cases:**

- Office-wide Signage or Dashboards
- A screenspace per meeting/conference room
- Other

## Installation & Configuration

Lygos should be downloaded for each device you will be using, these include devices connected to screens, devices that will act as control or management clients and also device that will act as the server. Each Lygos Network should contain 1 server instance. That means one of the PC devices running Lygos Software should be in local mode (server) and others should connect to it with remote mode.

You can use one of the devices that display screen, control or management clients as the server. However, we recommend having a separate PC other than videowall screen nodes to assign as server if you have a large videowall.

### PC - Server Mode (Local)

A PC version of the software in Local (Server) Mode

**Steps:**

- Download Lygos Software from <https://lygos.io/download>
- Install it on a PC (Windows/MacOS/Linux)
- Launch the software
- Select Mode: Local (which is default)
- Press Start the Server Button

![](TODO...)![](TODO...)

Once successfully started the button will show "Server Ready" and IP address of the Server. Afterwards, you can create clients on the same computer.

- - Screen Clients
    - Management Clients (without restrictions)
    - Control Clients

All screen clients, whether launched locally or remotely, will appear in the Display Module and can be added to Screenspaces to form seamless videowalls where each act as a distributed screen node.

### PC - Client Mode (Remote)

A PC version of the software in Remote (Client) Mode

**Steps:**

- Download Lygos Software from <https://lygos.io/download>
- Install it on a PC (Windows/MacOS/Linux)
- Launch the software
- Select Remote Mode
- Fill the Connection Info on the Button and Press to Connect

![](TODO...)

- 1. IP Address: Can be obtained from the launcher of the server
  - Password/Key: You can use either
    - Master Keys: Can be obtained from an admin level management clients
    - User Keys: User keys can be created at admin level management clients
  - Security Token: This is optional security measure. It enables secure communication between server and that client. If not entered, the client will send communication obfuscated but not secure, also all file communication will be in plain.

Security Tab on Admin Level Management Client where Master Keys are shown and User Keys can be created:

![](TODO...)

- Afterwards, that client can summon Management, Control or Screen windows depending on Access Level

## Client Types

Lygos supports multiple [client types](https://lygos.io/docs/setup/client-types) to accommodate different management and control scenarios.These three main client types, all summoned from the same software. PC Version of the software can summon multiple clients. Tablet Versions can display a single client of choice.

### Screen Client

A screen area where maps, visualizations and media can be deployed to it remotely from Management Clients. Multiple visualizations can be deployed to screens in a grid format.

![](https://lygos.io/images/docs/setup/clientTypes_distsributedscreens.png)

Screen can be single or part of a larger screenspace (video wall) and allows displaying partial or full visualizations.

[Screen clients](https://lygos.io/docs/display/summon-screen-clients) are synchronized, so if you deploy a visualization to a region of a screenspace that corresponds to multiple screen clients even on different devices, they

animate/interact/render collectively as in one seamless screen. You can simply summon these clients from launcher and move their windows to any monitor/display you want. Lygos remembers locations of these clients on restart or relaunch and resummon them on their last location.

### Management Client

Management client is the core of the application where users can:

- [Setup/Configure screenspaces](https://lygos.io/docs/display/create-screenspaces) for your video walls and dashboards.
- Remotely turn on and off the PCs of your screen nodes or restart them.
- Add/Connect Data Files, APIs, Databases.
- Create/Edit custom Visualizations or with connected Data (maps, sensors, media, charts, etc.)
- Control and Configure Maps and Visualizations through their editors.
- Create Signage Loops and Multi-screen Presentations that span to whole video wall.
- Create Data Analytics.
- Access to Lygos Server Settings.

![](https://lygos.io/images/docs/setup/clientTypes_layout-w-visualizations.png)

### Control Client

By summoning a Control Client users can:

- Interact with deployed visualizations through simplified control UIs
- Point and draw on the videowalls/dashboards through mouse or touch
- All controls and interactions can be reverted as they are temporary for that session.
- Users can access Control Client by either using master control key, which gives access to control to all screenspaces or use a Control QR of a screenspace on a tablet to access to control of that screenspace only.

![](https://lygos.io/images/docs/setup/clientTypes_client-types-3.png)

##

## Mobile Client

Mobile clients include an Air Mouse to point and draw on the video wall screens and simplified controls for presentations. Multiple users can use Air Mouse simultaneously.

Mobile client can be accessed through scanning a control QR from a smart phone.

- Use your smart phone as an Air Mouse for your video walls or dashboards (does not require an application to be installed on the device.)
- Control Deployed Presentations

To Access Control QR From Management Client, Open Security or QR page depending on your access level on bottom left of your screen. From This page you can display a control QR Control QRs provide controls per Screenspace access.

## Access Levels & Keys

Lygos uses [level-based access control,](https://lygos.io/docs/setup/access-levels-and-keys) not permission or role-based authentication. Access is managed through different keys, each granting a specific level of functionality.

### Key Types & Access

_Screen Key_

- Can only summon screen clients
- Shown on the Launcher window of the Server or Settings in Management Clients
- Minimal access to system resources (security-wise)
- To be used on screen clients who are not supposed to control or manage

_Control Key_

- Can summon control clients
- Shown on the Launcher window of the Server or Settings in Management Clients
- These clients interact with visualizations and control screenspaces on limited scale which can be reverted after sessions.
- Cannot edit/configure layouts, visualizations, media
- Compared to the Control QR, this can control all scnreenspaces

_User Keys_

- Created via Management Clients with higher privileges
- Limited editing abilities: Can edit layouts, cannot edit screenspaces (Videowall Setup), Cannot use power functions (e.g., wake/restart/shutdown) of screens
- Ideal for non-admin users needing access to visualization, media, map configuration and layout deployment.

_Management Key_

- Allows full use of Management Clients.
- Can configure/edit/control all visualization, media, maps, layouts.

_Super Admin Access (Management Client summoned from Server itself)_

- Full administrative privileges
- Can create and manage all keys, screenspaces, and configurations

Only Remote Users connecting with Management Key and Management Clients summoned from Server itself are Admin Level Management Clients. These clients compared to other management clients can add, edit, delete screens, layouts,

screenspaces and have other admin level privileges.

### Ports

These Ports have to be open on Server, Clients and in between to Lygos to operate:

| 37349 | Server - Client Communication |
| ----- | ----------------------------- |
| 37777 | Server - Client Communication |
| 37214 | Server - Client File Transfer |

# [DISPLAY](https://lygos.io/docs/display)

The Display Module relies on three primary components to function: the Screen, the Screenspace, and the Layout.

- **Screen:** This is where screen clients, initiated from both remote and local Lygos applications connected to the server, are displayed. These screens can then be added to your designated Screenspaces.
- **Screenspace:** Think of this as a digital canvas that mirrors your physical dashboard or video wall. You populate this area by loading screens and organizing them into a structured grid.
- **Layout:** These are the visual arrangements placed onto your screenspaces. You can design layouts, position visualizations anywhere on the grid, and easily load, switch, or remove them.

**Key Features:**

- **Create Screenspaces:** Build and administer the areas used to organize your display hardware.
- **Load Screens:** Allocate individual screens from your video walls or dashboards into your chosen screenspaces.
- **Replace & Resize Screens:** Modify the grid placement and dimensions of your screens.
- **Create Layouts:** Craft specific design arrangements tailored for your screenspaces.
- **Switch Layouts:** Transition smoothly between various layout designs whenever required.
- **Load Visualizations:** Push your content and data visuals directly into active layouts.
- **Replace & Resize Visualizations:** Tweak the position and size of your visual content across the layout grid.

## [](https://lygos.io/docs/display/summon-screen-clients)Summoning Screens

Screen Clients are summoned from Lygos Software Instances and act as a full or partial screen area that visualizations and media can be deployed remotely.

There are various options to setup your videowalls and dashboards.

In Lygos Launcher, press Summon Screen, This will create a screen window:

![](https://lygos.io/images/docs/display/summonScreenClients_summon-screen-clients-1.png)![](https://lygos.io/images/docs/display/summonScreenClients_summon-screen-clients-2.png)

On the left you can see ID of the screen, on the right, you can see QR code of the screen. On this mode, the screen is not assigned to a screenspace yet.

You can either manually place screens on screenspaces, or use a tablet client to auto place them by scanning QRs (On Management Client of a Tablet Client → Display Module -> On Right Action Menu → Scan Screens).

You can drag this screen to anywhere from its toolbar and than fullscreen or multiscreen it.

**Fullscreen:** It puts the screen on the fullscreen mode on the display/monitor it is on. **Multiscreen:** It puts the screen on fullscreen on multiple displays. There are 3 modes, horizontal, vertical and grid (2x2). These displays should be at same resolution and adjacent to each other. You can use horizontal and vertical for videowall columns and rows. As a result, it creates a single screen client per row or column. For small videowalls up to 4 screens, you can use the grid mode to create 1 screen client that covers all 4 displays/monitors of the small videowall.

![](https://lygos.io/images/docs/display/summonScreenClients_summon-screen-clients-3.png)

Here is button on the top right of a screen and their functionality:

The summoned screen clients will appear on Management Clients of that Lygos Server. You can add these screens to screenspaces, deploy partial/full visualizations to them.

![](https://lygos.io/images/docs/display/summonScreenClients_summon-screen-clients-4.png)

Screens clients created on Lygos software connected to the server automatically show on this tab.

As a result, screen clients become a seamless screen area to deploy visualization:

![](https://lygos.io/images/docs/display/summonScreenClients_summon-screen-clients-5.png)

You can see these screens are part of screenspace, compared to the unloaded mode on the top of the page and show id is toggled on for this screenspace so they show an info overlay.

## [](https://lygos.io/docs/display/create-screenspaces)Creating and Managing Screenspaces

Screen clients summoned on distributed computer nodes connected to the video wall displays or dashboards can be virtually assigned to a grid.

This assignment allows us to seamless synchronization and dynamic visual deployment across group of screens.

For example, you can represent 12 videowall displays in 3x4 as a seamless screenspace, or 3 dashboards on office corridor, this flexible screenspace formation enables users to represent any screen group as a screenspace.

![](https://lygos.io/images/docs/display/createScreenspaces_create-screenspaces-1.png)

### Creating a New Screenspace

Press the **"+"** button in the **Screenspaces Menu** to create a new screenspace.

During creation, you can configure:

- Screenspace Name
- Bezel Size
- Logo

![](https://lygos.io/images/docs/display/createScreenspaces_create-screenspaces-2.png)

These settings can be revisited and modified anytime by pressing the **Settings** button next to a name of the screenspace in the menu.

### Navigating Screenspace View

Select a screenspace from the menu by clicking on its name. The Screenspace View displays:

- A **grid layout** of the screenspace
- A **list of screens** currently connected to the server

### Summoning and Managing Screens

Screens can be summoned from any computer connected to the same server via the **"Summon Screen"** button on their launchers.

Once a screen is created on the server, it will appear as a **card** in the **Screens tab** of the Screenspace View.

**Screen Status Indicators:**

| **Blue**: Screen is loaded to this screenspace        |
| ----------------------------------------------------- |
| **White**: Screen is not loaded to any screenspace    |
| **Gray**: Screen is loaded to a different screenspace |

### Loading and Arranging Screens

Use the **Load** and **Unload** buttons on each screen card to assign or remove screens from the screenspace.

Adjust screen **positions** by dragging them from the center. Resize **inner grid dimensions** by dragging from the corners.

### ![](https://lygos.io/images/docs/display/createScreenspaces_create-screenspaces-3.png)

The inner grid dimensions define the layout capacity of visualizations on that screen

- **1×1 grid**: One visualization can be deployed
- **2×2 grid**: Up to four visualizations (1×1 each) or one large 2×2 visualization, or any valid combination within the space

This layout system allows flexible arrangement and sizing of visuals to match your display strategy.
![](https://lygos.io/images/docs/display/createScreenspaces_create-screenspaces-4.png)

## [Creating and Managing Layouts on Screenspaces](https://lygos.io/docs/display/create-layouts)

Layouts define how visualizations are arranged across a screenspace. You can manage and create layouts via the **Layouts Menu** in the **Display Module**.

Visualizations that span into multiple screen clients render/interact/animate synchronously. As a result, you can use a videowall as a seamless screen and deploy collages of visualization in any formation.

### Default Layout

- When a new screenspace is created, a blank layout named **"Default"** is automatically generated for it.

![](https://lygos.io/images/docs/display/createLayouts_create-layouts-1.png)

### Creating a Layout

Select a screenspace to create a layout (It can be migrated to other screenspaces later on)

In the Layouts Menu, press **"+"** to create a new layout. During layout creation, you can:

- **Name** your layout
- **Select** the target **screenspace**
- **Choose a custom theme** for the layout (or use the global theme if preferred - see **Themes**)

![](https://lygos.io/images/docs/display/createLayouts_create-layouts-2.png)

These settings can be updated anytime by pressing the **Settings** button next to the layout in the Layouts Menu.

### Transferring Layouts Between Screenspaces

You can reassign a layout to a different screenspace from the layout's settings.

**Keep in mind: Screen configurations** (like screen count, grid sizes, or positions) may vary between screenspaces. Transferring a layout could affect the **relative positioning** of visualizations.

### Deploying Layouts

Use the **toggle on** button next to a layout to deploy it to its assigned screenspace.

- This action automatically **undeploys the currently active layout** in that screenspace.
- Only **one layout** can be active in a screenspace at any given time.

To **clear a layout** and show a blank screenspace, press the **toggle off** button on the active layout.

### [Deploying Visualizations to the Video Wall](https://lygos.io/docs/display/deploy-visualizations)

Once in the Layout View:

- Go to the **Visualizations Tab**.
- **Select a visualization type** from the menu. A list of visualizations of that type will appear.
- You can:
  - **Drag a visualization card** to the layout grid, or
  - **Click the card** to open a right-side options menu and use **Load/Unload** to deploy it.
  - Alternatively, you can press "All" button on Visualization menu, and text search the visualization from all visualizations.

**Card Border Colors Indicate Module Types:**

| **Gray**   | Not deployed in the current layout |
| ---------- | ---------------------------------- |
| **Orange** | Media                              |
| **Yellow** | Visualization (Charts)             |
| **Green**  | Map                                |
| **Pink**   | Story                              |
| **Red**    | Signage Loop                       |
| **Purple** | Expert                             |
| **White**  | Assignable Region                  |

Deployed visualizations will appear on the layout grid. You can:

- **Drag and resize** them freely
- See **screen outlines** in the background (blue rectangles) for reference

![](https://lygos.io/images/docs/display/deployVisualizations_deploy-visualizations-1.png)

### Visualization Tab - Special Tools

The first three options in the **Visualization Tab** are tools (not visualizations):

**Deployed**: Shows a list of visualizations already deployed in the layout.

![](https://lygos.io/images/docs/display/deployVisualizations_deploy-visualizations-2.png)

**All**: Lets you search and access any visualization in the system:

![](https://lygos.io/images/docs/display/deployVisualizations_deploy-visualizations-3.png)

**Assign**: Allows you to load **slots** into the layout grid. You can then assign or replace visualizations within these slots using the **Visualization Editor's Assign** function.

![](https://lygos.io/images/docs/display/deployVisualizations_deploy-visualizations-4.png)

### Quick Controls on Visualization Cards

When you select a visualization card, you'll see the following options:

- **Load / Unload** - Add or remove the visualization from the layout.
- **Config** - Opens the full editor for that visualization.
- **Control** - Opens a compact control panel.
- **Preview** - Shows a live preview of the visualization.
- **Reset** - Resets all control changes made (Reverting a Session).
- **Exit** - Deselects the visualization.

## [](https://lygos.io/docs/display/power-options)Power Options of Screenspace

In the **Display Module > Screenspace View**, you can manage the **power settings** for computers hosting connected screen nodes.

You can perform these actions:

- **Individually**: via each screen's card
- **Collectively**: via the right-side **Quick Menu** for the entire screenspace (videowall or dashboard group)

### Available Power Options

- **Relaunch Screens**
  - Restarts the Lygos application on the selected machines.
  - The app will reopen windows in their last saved positions.
- **Wake Screens**
  - Sends **Wake-on-LAN** packets to power on machines remotely.
  - Requires **Wake-on-LAN enabled** in BIOS
  - Devices must be on the **same local network**
  - If **Auto-Launch** is enabled, Lygos starts with the OS and restores windows to their last positions.
- **Reboot Screens**
  - Reboots the entire OS of the target machines.
  - If **Auto-Launch** is enabled, the Lygos app will start automatically on boot and restore previous window positions.
- **Turn Off Screens**
  - Shuts down the operating systems of the selected machines.
  - Devices can be powered back on using **Wake Screens** (if Wake-on-LAN is enabled in BIOS).
- **Update Screens**
  - Checks for updates on the screen launchers.
  - Installs any updates and **relaunches screen clients** afterward.

  ![](https://lygos.io/images/docs/display/powerOptions_power-options-1.png)

**Deleting a Screen** Only **closes the screen window** on the target machine. It does **not exit the Lygos application** on that machine.

## [](https://lygos.io/docs/display/video-wall-automation)Video Wall Automations

You have the ability to automate your **screenspaces** through the use of scheduled event triggers. By linking a predetermined action to a specific time, your display environment can manage itself autonomously, removing the requirement for manual user input.

**Available Actions:**

The software allows you to queue up the following automated actions:

- **Change Layout:** Automatically swaps the screenspace over to a pre-configured, designated layout at the set time.
- **Wake Screenspace:** Triggers the network to power up the connected computers and launch the screens.
- **Relaunch Screenspace:** Completely restarts the connected hardware and screen clients to clear memory and refresh the system.
- **Shutdown Screenspace:** Initiates a safe power-down sequence for the screen clients and their host computers.
- **Clear Drawing:** Automatically wipes out any digital annotations currently drawn on the display.
- **Reset Controls:** Restores all interactive elements back to their baseline default configurations.
- **Show Labels:** Turns on the informational identification labels across all visuals on the screenspace.
- **Hide Labels:** Turns off the identification labels to provide a pristine viewing canvas.

![](https://lygos.io/images/docs/display/videoWallAutomation_video-wall-automation.png)

## [](https://lygos.io/docs/display/point-and-draw)Point and Draw

The **Point and Draw** functionality, accessible via the **Control** and **Management Clients**, transforms your standard dashboard or video wall into a highly interactive **whiteboard** environment.

**Key Features:**

- Every distinct **Layout** possesses an independent **Drawboard**.
- Whenever a Layout is pushed live, its associated Drawboard is automatically activated alongside it.
- Any digital pointers or ink lines are rendered as a top-layer overlay, floating above your active media and data.

### Activating Point/Draw Mode

- Navigate to your **Layout View**.
- Click the **Pointer/Drawing button** to turn the system on.
  - You will see a **shadow overlay** appear over the layout grid, confirming the system is active.
- Drag your finger or mouse across the grid:
  - Hovering will project a corresponding **pointer** directly onto the physical displays.
  - Clicking and dragging your cursor will actively **draw lines** that render on both the layout interface and the live screens simultaneously.

  ![](https://lygos.io/images/docs/display/pointAndDraw_point-and-draw-1.png)

### Multiplayer Drawing

- The software supports **multiple clients** engaging with the drawing and pointing tools at the exact same time on a shared layout.
- When utilizing **tablets**, the system relies entirely on **touch gestures**, meaning no floating cursor will be visible.

![](https://lygos.io/images/docs/display/pointAndDraw_point-and-draw-2.png)

### Drawing Controls & Options

You have access to a suite of customization tools via the **right quick action menu** found inside the Layout View:

- **Change Pointer Color**
- **Adjust Pointer Size**
- **Clear All Drawings**

To cease drawing interactions:

- Click the **Pointer/Drawing button** to toggle it off.
  - This action simply hides the control overlay **on your device only**.
  - Any existing ink remains visible on the video wall until it is manually wiped.
- To completely wipe all ink from the physical displays:
  - Click the **Clear Drawings** button situated in your Layout View.

## [](https://lygos.io/docs/display/visualization-labels)Visualization Labels

You have the ability to attach **labels** to your deployed content, supplying a customized **name** and a supplementary **description**. These textual labels serve to define and identify the various elements occupying your video wall.

- You can toggle these labels on and off utilizing the **Show Labels** toggle located within the right-side menu of your selected layout.
- When this feature is active, the visualization's **current state**, **description**, and **name** are rendered directly onto the display as a text box.
- Certain media elements and interactive visualizations feature an additional, independent label window designed specifically for their state. For instance, a document might broadcast its current page number, or a video might show its timestamp and total duration. The software allows you to disable these specific state labels independently via the item's configuration settings.
- The visual styling of these labels-such as their colors, text format, location, and size is governed by the Theme linked to the active Layout. If no specific layout theme is chosen, the system defaults to the Global Theme. You can modify Themes via the Settings menu, and apply them to Layouts through the Layouts Edit Menu.

![](https://lygos.io/images/docs/display/visualizationLabels_visualization-labels-1.png)

## [](https://lygos.io/docs/display/custom-background)Custom Background

Enhance your setups by applying **custom backgrounds**, such as brand messaging or corporate logos, directly to your dashboards and video walls. These backgrounds render **behind your visualizations**, injecting a layer of branding and personalization into the space. The software intelligently scales the background to fit the entirety of the screenspace. This means a video wall will display one large, continuous logo stretching across all connected displays.

### Accessing the Background Settings

- Navigate into the **Screenspaces Menu**.
- Locate the specific screenspace and click its **Configure/Settings button** (the gear icon).
- Scroll down to the **Custom Background** category.

### Background Options

The system provides **three background types** to choose from:

- **Default:** This renders the standard **Lygos logo**.
- **Image:** This allows you to upload a personalized **SVG image**. You gain access to tweak the following attributes:
  - **Size**
  - **Color Filter**
  - **Transparency**
  - **Grayscale Mode**
- **Text:** This option projects custom **text** onto the background canvas. You can freely customize the:
  - **Text Size**
  - **Text Color**
  - **Font**
  - **Transparency**

![](https://lygos.io/images/docs/display/customBackground_custom-background-1.png)

### Additional Background Setting

- You maintain the ability to alter the underlying **background color**, independent of the logo or text type you have selected.

## [](https://lygos.io/docs/display/adjust-bezels)Adjust Bezels

When broadcasting visuals over a grid of monitors, **ignoring bezel sizes** typically introduces **visual artifacts**. This is highly disruptive when shapes, lines, or text block span across multiple screens, becoming especially jarring at the **corners and edges** of the displays. Lygos mitigates this issue by calculating the bezel width and creating an overdraw effect equal to the bezel size in relation to the physical screen. You can inspect these artifacts and calibrate your bezels directly from the Screenspace View within the Display Module.

![](https://lygos.io/images/docs/display/adjustBezels_adjust-bezels-4.png)

### How to Adjust Bezels

- Navigate to the **Screenspace View** located in your Display Module.
- Expand the **Quick Action Menu** and click on **Show Test**.
  - This action projects calibration test patterns onto all of the physical screens, making misalignments obvious.
- If the white test lines appear disjointed or broken across the screen gaps, a **bezel adjustment is needed**.
- Click the **Configure** gear icon associated with that screenspace.
- Manipulate the **bezel size sliders** until the test pattern aligns **perfectly** across all connected displays.

![](https://lygos.io/images/docs/display/adjustBezels_adjust-bezels-5.png)

# [](https://lygos.io/docs/data)DATA

As a visual data analytics software designed for video walls and dashboards, Lygos provides several methods to import or stream information from various sources. You can use these sources to feed your interactive and real-time data visualizations. There are multiple categories of data that Lygos can handle:

### File Based Data Types

These data types can be created and modified using custom local editors built into the software. You can also import and export these datasets in several file formats. Supported formats include:

- Spreadsheet: Tabular Data with Columns and Rows
- GeoData: Spatial Data corresponding to KML or GeoJSON
- GraphData: Nodes with Links/Edges
- TreeData: Trees with Children and Branches.

### Streaming Data Types

This category allows you to pull live information directly into your visualizations from local or remote databases and APIs. Supported Databases include:

- MongoDB
- Azure SQL
- MySQL
- Oracle
- DynamoDB
- SQLite
- IBM Db2
- Cassandra
- Microsoft SQL Server
- Elasticsearch
- BigQuery
- MariaDB
- Neo4j
- PostgreSQL
- Redis
- Snowflake

Other Streaming Sources include:

- REST API: Periodic Queries to Remote Rest API endpoints.
- REST Service: Creating REST API endpoint at the Lygos Instances for Remote Connections.
- MQTT: Sensor and IoT Publish/Subscribe
- Filewatch: Watching Files

### Other Data Types

- TileSource: Remote Map Tile Sources

## [](https://lygos.io/docs/data/data-format)Data Format

Data formats are essential because they dictate exactly which visualizations are compatible with your information on the video wall. For example, map data containing geographical coordinates is classified as Spatial, whereas yearly sales figures containing dates are categorized as Temporal.

You can determine your proper format easily by using the Data Format UI tool. This tool lets you analyze raw information, define its underlying structure, and assign dimensions to build a proper schema.

![](https://lygos.io/images/docs/data/dataFormat_data-format-1.jpg)

Once your schema is set, the system calculates all compatible visualizations and summarizes the results using specific data tags. These tags act as a guide to show you exactly where your data will work, since certain visualizations require highly specific formatting.

Note: For file based sources, Lygos determines the format automatically. The only exception is spreadsheets, where you must manually assign a type for each individual column.

![](https://lygos.io/images/docs/data/dataFormat_data-format-2.png)

### Summary of Data Tags

- **Dimensions:** This represents the number of columns or value fields in your data. Visualizations like Boxplot, Candlestick, Chart3D, ParallelLine, ParallelScatter, and ThemeRiver require two or more dimensions. Options like Chart, Funnel, Gauge, Indicator, Pie, Polar, Radar, and Timeline need at least one dimension.
- **Temporal:** This indicates data containing DateTime values. It is required for any visualization that supports animation.
- **Collection:** This tag applies when data is structured as an array or dictionary. While it does not restrict specific visualizations directly, it can impact your available dimensions.
- **Spatial:** This denotes geographical GIS data requiring latitude and longitude coordinates. It is necessary for map visualizations utilizing marker, icon, cluster, or heatmap layers.
- **Identifier:** This tag means the data contains a specific name or ID, which is required for map tracking layers.
- **Territorial:** This identifies choropleth map data and requires a specified territory like a country, city, or region.
- **PointCloud:** This represents Lidar data and strictly requires X, Y, and Z coordinates to function.
- **Graph:** This denotes data containing nodes and edges, required for Graph and Sankey visualizations.
- **Tree:** This tag applies to flat or nested tree structures used in Tree, Treemap, and Sunburst visuals.
- **Sensor:** This requires a name and a reading value to properly feed Sensor visualizations.
- **Geojson:** This utilizes GeoJSON or KML files specifically for map layers.
- **Messages:** This format handles events or messages that require a title and a description, with optional string categories.

## [](https://lygos.io/docs/data/spreadsheet)SpreadSheet

The Spreadsheet tool functions as a local data source built specifically for handling and editing tabular information. Once populated, this data feeds directly into your video wall visualizations to construct map layers and charts.

### Importing and Exporting

- **Supported Formats:** You can bring in or export your spreadsheets utilizing CSV, XLSX, JSON, and XML file types.
- **Exporting:** When you are ready to export your information, you must specify your chosen format among CSV, XLSX, JSON, or XML.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-1.png)

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-2.png)

### Editing the Table

**Adding and Removing Rows:**

- **Add Rows:** Simply press the Add Row button located on the bottom menu bar to insert a new line.
- **Remove Rows:** Highlight the rows you wish to delete and press the Remove Row button.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-3.png)

**Adding and Removing Columns:**

- **Add Columns:** Type in your desired column name and press the Add Col button to create it.
- **Remove Columns:** Press the X icon situated in the top right corner of any column to delete it.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-5.png)

**Editing Cells:**

- Click on any individual cell and type your new value to update its contents.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-7.png)

**Resizing Columns:**

- Click and drag the vertical separators between columns to manually adjust their width.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-8.png)

**Navigating the Table:**

- Utilize the pagination controls situated at the bottom of the editor to flip through pages or skip immediately to the beginning or end of your document.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-9.png)

### Sorting and Filtering

**Sorting Rows:**

- You can organize your rows by picking a specific column and selecting either descending or ascending order.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-10.png)

**Filtering Rows:**

- You can filter your rows based on specific cell values. Keep in mind that applying filters within this editor does not alter the data being sent to your active maps or visualizations.
- You can customize these filters utilizing logical operators and search strings.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-11.png)

### Data Formats and Visualization Integration

- **Assign Data Formats:** You must assign specific data formats to your columns before they can be utilized in visualizations.

![](https://lygos.io/images/docs/data/spreadsheet_spreadsheet-13.png)

- Examples:
  - Labeling a column as Time unlocks temporal animations within your visualizations.
  - Labeling a column as Coordinates permits the data to function correctly on map layers.
- **DataFormat Tags:** These indicator tags are visible in the top right corner of your editor and display the formats currently supported by your source.
  - Certain visualizations demand specific tags to function properly.
  - If your data source is missing from the visualization selection menu, you should verify that it possesses the required tags.

## [](https://lygos.io/docs/data/geo-data)GeoData

**GeoData** acts as a local editor and data source specifically for the GeoJSON format, allowing you to manipulate and import GIS data. This information is primarily used to populate GeoJSON layers on your video wall maps.

**Note:** Because this is strictly a data source and not a visualization editor, any map settings you adjust here, such as the view center or styling, are temporary. These visual settings will not translate to the final visualizations utilizing this data.

### Importing and Editing GIS Data

You can export or import your GIS files utilizing KML and GeoJSON formats. You also have the option to generate a completely blank map and manually construct elements using either the map interface itself or the JSON editor panel located on the right.

![](https://lygos.io/images/docs/data/geoData_geodata-1.png)

### Adding and Editing Layers

The left menu within the map editor provides tools to modify or add specific layers, including polylines, polygons, and markers. You can also use this area to establish a default center view and adjust your zoom level.

![](https://lygos.io/images/docs/data/geoData_geodata-2.png)

### Layer Tools

Pressing the **Edit Layers** button unlocks several manipulation actions:

- Cut layers
- Drag layers
- Remove layers
- Rotate layers

![](https://lygos.io/images/docs/data/geoData_geodata-3.png)

### Dynamic Map and JSON Interaction

Whenever you make a visual change to the map, the corresponding JSON data on the right panel updates in real-time. Conversely, altering the raw JSON data will instantly update the shapes and layers on the visual map.

![](https://lygos.io/images/docs/data/geoData_geodata-4.png)

### JSON Editing

Typing new values directly into the JSON editor immediately repositions or alters the properties of your map layers.

![](https://lygos.io/images/docs/data/geoData_geodata-5.png)

### Supported Formats

This specific data source exclusively supports spatial information structured in the **GeoJSON** format.

![](https://lygos.io/images/docs/data/geoData_geodata-6.png)

### Adding Properties to Map Elements

If you want to attach specific data values to your map elements, your GeoJSON features must contain properties. Imported files may already have these properties attached to their features. If they are missing, you can insert them manually via the JSON editor. Once added, these values become available for your maps and visualizations.

## [](https://lygos.io/docs/data/graph-data)GraphData

**GraphData** serves as your local editor and source for graph based information. This data type feeds directly into Sankey and Graph visualizations on your video wall.

### Importing and Editing Graph Data

You can bring in or export your graph files using JSON, GRAPHML, and GEXF formats. You can also launch a blank canvas and construct your graph manually by dropping links and nodes, or by coding them directly into the JSON editor.

### Adding Nodes and Links

**Adding Nodes:**

Activate the **Add Node** toggle located on the bottom menu. Next, simply click any empty space on your graph canvas to drop a node into that exact spot.
![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-1.png?alt=media&token=1e993a0d-e1ef-48d0-b37b-b4b7c2ec2c5f)

**Adding Links:**

To connect two points, activate the **Add Link** toggle, pick your starting node, and drag the connection over to your destination node:

- **Mouse Input:** Click your source node, hold the button down while dragging to the target, and release to connect.
- **Touch Input:** Tap the source node, slide your finger to the destination node, and lift to connect.

![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-2.png?alt=media&token=0e77f73d-ba74-4f74-a165-113ded493b7f)

### Editing Nodes and Links

**Node Properties:**

You can modify the Value and Name of any node by selecting it and utilizing the bottom menu to input your new data.

![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-3.png?alt=media&token=a24a0ffc-8cc7-4796-b511-66680e28bd73)

**Link Properties:**

You can define your links as undirected or directed by adjusting the setting in the bottom menu.

![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-4.png?alt=media&token=198471fb-abdc-452e-a6a4-5729dff060e2)

### Auto Locate Feature

The **Auto Locate** function automatically calculates and reorganizes the positions of all your nodes based on their connecting links.

**Warning:** Once triggered, this reorganization cannot be undone!

![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-5.png?alt=media&token=5d055820-7b39-42db-908d-503e2d3d37e0)

### Supported Data Format

This editor strictly utilizes the **Graph** format, which is essential for Graph Visualizations and Sankey diagrams.

![](https://firebasestorage.googleapis.com/v0/b/lygos-io.firebasestorage.app/o/docs%2Fdata%2FgraphData_graph-data-6.png?alt=media&token=9fea582d-85d4-451c-b42e-4819753ac44a)

## [](https://lygos.io/docs/data/tree-data)TreeData

**TreeData** operates as a local editor and source for hierarchical tree structures. This specific data feeds your Sunburst, Treemap, and Tree visualizations.

### Importing and Editing Tree Data

You can export and import your tree files exclusively in the **JSON** format. You may also open a blank tree structure and manually append child nodes.

![](https://lygos.io/images/docs/data/treeData_tree-data-1.png)

### Adding and Managing Nodes

**Adding Nodes:**

- **Add Root Node:** Press the plus button located in the top frame to generate a new root node.
- **Add or Remove Child Nodes:** Utilize the remove or add buttons situated on the right side of any existing node to manipulate its children.

![](https://lygos.io/images/docs/data/treeData_tree-data-2.png)

**Editing Nodes:**

- **Edit Name and Value:** Press the pen icon to alter the assigned value and name of your selected node.

![](https://lygos.io/images/docs/data/treeData_tree-data-3.png)

### Viewing and Filtering Nodes

- **Display or Hide Child Nodes:** You can easily collapse or expand the visibility of any parent node's children.
- **Filter Nodes by Name:** Utilize the search filter to quickly locate specific nodes based on their assigned names.

![](https://lygos.io/images/docs/data/treeData_tree-data-4.png)

### JSON Editor Integration

You can modify node values, names, and other custom fields directly within the JSON editor panel.

- Root nodes populate as objects within a primary array.
- Child nodes exist inside their parent's object under a dedicated children key.

![](https://lygos.io/images/docs/data/treeData_tree-data-5.png)

### Supported Data Format

This tool exclusively outputs the **Tree** data format, which is required for Sunburst, TreeMap, and Tree Visualizations.

![](https://lygos.io/images/docs/data/treeData_tree-data-6.png)

## [](https://lygos.io/docs/data/file-watch)FileWatch

The FileWatch tool allows you to monitor specific files stored on your server and utilize them as dynamic data sources. Whenever the watched file undergoes a change, Lygos processes it as a data update and feeds it directly to the visualizations on your dashboards.

**Supported File Types**

- CSV
- XLSX
- JSON
- XML
- TXT

**Live Data Updates** Once you import a file, the FileWatch system creates a copy on the server and monitors it continuously. Any external edits or changes made to this server copy are automatically pushed to your active visualizations in real-time.

**Use Cases** If you utilize an external analytics process that constantly dumps new information into a file, you can link Lygos to watch that specific document. You can specify the exact format of this file using the Data Format Tool. The tool converts the file contents into JSON format so it can be structured and read easily by the software.

![](https://lygos.io/images/docs/data/fileWatch_file-watch-1.png)

## [](https://lygos.io/docs/data/database)Database

You can connect directly to a massive variety of databases to stream information to your video walls.

**Supported Databases**

- **Relational:** Oracle, MySQL, Microsoft SQL, PostgreSQL, SQLite, MariaDB, IBM DB2, Azure SQL, Google Bigtable, and Snowflake
- **NoSQL:** MongoDB, Redis, Amazon DynamoDB, Cassandra, and Neo4J
- **Search Engines:** Elasticsearch

**Key Features**

- You can establish multiple unique queries for every connected database.
- Every query counts as its own Data Source that can be assigned to your visualizations.
- Connection parameters will vary depending on the specific database type you are using.
- **Query Options:** You can input specific connection options like targeting a particular table or collection.
- **Database Query:** You have a dedicated pane to enter the exact query you wish to execute.
- **Polling Frequency:** You completely control how often Lygos checks for refreshed information.
- **Data Window Size:** This dictates how many past results the system stores in memory, which is essential for data animation. If your data lacks DateTime values, the system uses the exact time it was received instead. For instance, polling every minute with a window size of 60 gives you a full hour of animated data points on your maps.
- **Data Polling Mode:** You can set your query to run On Demand or On Background. On Demand pulls data temporarily and only when a visualization is actively rendering it on screen. On Background pulls data persistently and saves your data window even if the application closes or relaunches.
- **Data Format:** You determine the structure of incoming database results using the Data Format Tool.
- **Preview Results:** You can view the Raw Data to see exact query results or database errors, and you can view the Formatted Data to see exactly how your source will look before applying it to a layout.

![](https://lygos.io/images/docs/data/database_database-2.png)

## [](https://lygos.io/docs/data/rest-api)Rest API

The Rest API feature connects to external endpoints to periodically poll information, while the Rest Service feature allows outside systems to post information directly to local APIs hosted on your Lygos Server. Both methods relay data updates to the visualizations on your video walls.

![](https://lygos.io/images/docs/data/restApi_rest-api-1.png)

**Rest API:** You can establish connection options via a URL link or input them manually into the configuration menu. Lygos supports three Basic Authentication types:

- Basic (Username and Password)
- JWT Bearer (Token)
- OAuth2 (API Key)

You can define the Default API, the Query API, and any Query Parameters. The software allows you to create multiple queries targeting the same host, port, authentication, and API. Additional configurations include:

- **Polling Frequency:** Controls how often data is refreshed.
- **Data Window Size:** Dictates how many past results are stored for animation purposes. Without DateTime values, the receival time is used.
- **Data Polling Mode:** Choose between On Demand for temporary active polling or On Background for persistent polling.
- **Data Format:** Formats the incoming feed via the Data Format Tool.

**Rest Service:** You can generate local Rest API points on your Lygos server utilizing your server IP address and a specific port. External clients can then Post, Put, and Patch to this URL. Clients posting data to this endpoint must provide Basic Authentication credentials. Because the data arrives directly at this endpoint, it processes according to your Data Format immediately and relays to your visualizations without relying on a Polling Frequency. Additional configurations include:

![](https://lygos.io/images/docs/data/restApi_rest-service-2.png)

- **Data Window Size:** Dictates how many past results are stored for animation purposes.
- **Data Polling Mode:** Choose between On Demand or On Background data retention.
- **Data Format:** Determines how the incoming post is structured.

## [](https://lygos.io/docs/data/sensor)Sensor (MQTT)

This module allows you to subscribe and connect to real-time data feeds utilizing the MQTT protocol. It is the perfect solution for pulling live data from sensors, IoT devices, or any other external system utilizing MQTT. The setup process functions very similarly to configuring a standard Database. The continuous live updates streaming from your sensors can be routed directly into the maps and visualizations active on your video walls.

![](https://lygos.io/images/docs/data/sensor_sensor-1.png)

- **Host and Port:** The URL address of your MQTT Broker and The specific port of your MQTT Broker.
- **Connection:** Choose from MQTT Unsecure, MQTT with TCP or SSL, Websocket Unsecure, or Websocket with TCP or SSL.
- **Username and Password:** Input these credentials if authentication is required.
- **Reconnect Timer:** This function pings the connection at your defined second interval and automatically resubscribes if the connection drops.
- **Data Window Size:** This dictates the volume of past results kept in memory.
  - This stored window is essential for driving visualization animations.
  - If your incoming data lacks datetime values, the system will substitute the exact receival time to allow for temporal animation.
  - As an example, if you poll data every minute and set a window size of 60, you will have a full hour of animatable data points.
- **Data Polling Mode:** Choose how your query operates in the background.
  - On Demand keeps data temporary, only polling when an active visualization is currently displaying it on a screen.
  - On Background makes the data persistent, polling constantly and saving the window memory even if the application is restarted or closed.
- **Data Format:** Utilize the Data Format Tool to structure the incoming MQTT feed.
- **Preview Results:** Validate your stream instantly.
  - Raw Data displays the unedited incoming MQTT feed.
  - Formatted Data shows the finalized structure after your formatting is applied.

## [](https://lygos.io/docs/data/data-window)Data Window

The **Data Window** is a core configuration setting that dictates exactly how the software manages, retains, and receives all incoming data streams. You can tweak these parameters to ensure your dashboards always have the proper historical context while maintaining optimal performance. Data sources including Sensor MQTT, RestService, RestAPI, FileWatch, and Databases all rely on this window parameter. As new data flows into a document, it is stored in the window; once that window reaches maximum capacity, the oldest data point is deleted to make room. You can define this maximum size by the total number of elements, raw file size, or a set time duration. The primary purpose of this window is to power data animations across your video wall. A window size set to one means the system discards everything except the absolute newest data point, resulting in a strictly real-time display. Expanding the window size and activating animation mode allows users to scrub through historical points or watch the data evolve over time. These animations synchronize across the entire video wall, meaning all maps and visuals will animate together across a shared timeline via Temporal Synchronization.

### Configuration Settings

- **Window Size:** This limits the absolute number of recent data updates the system holds. Setting the Window Size to 3 means Lygos keeps the three newest updates and purges anything older. This parameter is vital for Multi dimensional Charts and Animations.
- **Window Capacity:** This limits the total volume of retained data by megabytes. If the incoming data pushes past this MB limit, the oldest items are deleted to maintain the threshold.
- **Window Duration:** This sets a strict lifespan for your data. Any stored update that ages past your defined duration is automatically deleted, ensuring your window only contains relevant recent history.

### Operation Modes

Lygos offers two distinct modes for handling your data fetching operations:

- **On Demand:** Data is only accepted or fetched when it is actively needed. This happens when a visualization tied to the data is live on a screenspace, or when a user has the management client or editor actively open.
- **Background:** Data fetching begins automatically the moment your Lygos server boots up, and it continues to collect uninterrupted for as long as the server runs. Crucially, the data stored in this mode persists through complete server shutdowns and restarts, guaranteeing you never lose your historical context.

# [](https://lygos.io/docs/maps)MAPS

Lygos allows you to deploy interactive, multiple layer, and real-time or animated maps across a portion or the entirety of your video wall. This dedicated GIS mapping module is a critical component for executing visual data analytics within control room environments. Because the system utilizes distributed screen nodes, it can render these maps at full scale and resolution, achieving over 100 million pixels while seamlessly displaying thousands of individual elements or markers.

Operators can easily pan and zoom the video wall maps utilizing their control and management clients. Any interactions, user inputs, or configuration adjustments are instantly mirrored on the live video wall displays.

**Key Features**

- Operators can import data and apply specific filters.
- You can construct map layers utilizing your datasets and created filters.
- You have full control to configure each layer.
- The system supports deep interaction and data animation.

### Data & Logic

Before you can utilize geographical GIS information on your maps, you must first import the data into the Data Module using a supported geographical format. Once processed, these datasets become available to load directly into the Maps module. To understand the specific data requirements for each layer type, simply click the circled 'i' icon located in the header of the Data Tab to view examples and prerequisites.

### Datasets & Filters

This section showcases all of your currently loaded data sources.

- Use the toggle switch to activate the specific filters or datasets you wish to render on the map.
- Activating a dataset automatically reveals the Add Layer menu.
- Within the Add Layer menu, you can:
  - Assign a name to your new layer.
  - Pick an appropriate layer type that matches your dataset's underlying structure.
  - Apply various conditions and multiple filters to refine the dataset.
- Any filters you generate can be quickly toggled on or off as your requirements change.

### Layers

The Layers tab provides a comprehensive list of every layer currently added to your map.

- You can toggle the visibility of individual layers to hide or show them.
- You can reorganize their visual stacking order by dragging and dropping them within the list.
- The designated Base Layer will always remain positioned on top of the stack.

**Available Layer Types:**

- Tile Layer
- Geo Json Layer
- Territory Layer
- Marker Layer
- Icon Layer
- Cluster Layer
- Heatmap Layer
- Tracking Layer

### Settings

**Animation Settings:**

This section allows you to define the start and end times for your playback. These parameters correlate directly to the time values present within your data. Therefore, setting a start time of 2023 and an end time of 2025 will animate the mapped data occurring strictly within that two year window. The Animation Tab also provides controls for playback duration and other related adjustments.

**Base Layers:**

- **Base Layer:** This serves as the foundational tile layer for your entire map.
  - You can select a pre existing layer or utilize a TileSource to generate a customized tile background.
- **Base Overlay:** This functions as an optional secondary overlay layer.
- **Preset Overlays:** Traffic, Weather (Precipitation, Clouds, Wind, Temperature and Pressure), Graticule and Day Night Cycle on Video Walls.

**Layer Settings:**

- This area houses the general configuration options for your map layers.
- The available settings will shift dynamically depending on the specific layer type you have selected.

### Animation

The animation tab contains all of your playback controls. You may need to configure animation settings prior to using this and also have temporal data for animations.

- You can loop, stop, pause, or play your data animations.
- You can modify the overall duration of the playback sequence.
- You can crop the animation to focus on a highly specific time interval.

### Import Layers

If you have meticulously styled layers that you frequently rely on across various maps, you can utilize the import function to pull in those existing layers without needing to rebuild them from scratch.

## [](https://lygos.io/docs/maps/multiple-data-sources)Multiple Data Sources

The Map Module empowers you to load and visualize information sourced from several different geographical GIS datasets onto your video walls simultaneously.

- You can load multiple data sources provided they utilize recognized geographical formats, such as KML, GeoJSON, or CSV files containing coordinate columns.
- The system allows you to fluidly transition between these different sources or stack them across multiple layers, enabling you to thoroughly analyze and compare diverse sets of information on a single, unified map.

**How to Use:**

- Launch a Map Visualization from within the Visualization Editor.
- Proceed to the Data section of the interface.
- Add one or multiple compatible data sources to your project.
- Click the circled 'i' icon to review the specific Examples and Data Requirements associated with your chosen Layers.
- Utilize the Toggle Switch to actively insert or remove these datasets from your visual map.
- Once a dataset is added, you can utilize it to construct Custom Filters, and subsequently build new Layers derived from both those Filters and the original datasets.

![](https://lygos.io/images/docs/maps/multipleDataSources_multiple-data-saources-1.png)

## [](https://lygos.io/docs/maps/filters-and-layers)Filters and Layers

You can build specialized filters to narrow down and refine your map visuals based on specific data properties.

**How to Create a Filter:**

- Navigate to the Datasets & Filters tab within the interface.
- Press the Add Filter Button located next to your chosen dataset.
- Configure the following parameters:
  - **Dimension:** Pick a specific data field from your underlying dataset to evaluate.
  - **Expression:** Choose your desired comparison operator, such as =, >, <, or !=.
  - **Value:** Type in the exact value you wish the system to compare against.
- You can construct highly complex filters by linking multiple conditions together using OR and AND operators.

![](https://lygos.io/images/docs/maps/filtersAndLayers_filters-and-layers-1.png)

### Layer Creation and Ordering

Both your original datasets and your custom filters can be deployed onto the map as independent Layers.

**Add a Layer:**

- Inside the Datasets & Filters tab, toggle your desired filter or dataset to the active "on" position.
- This action prompts the Add Layer tab to appear on screen.
- You must provide:
  - A custom Layer Name
  - A specific Layer Type, keeping in mind that the available options are dictated by your data's format.
- Press Add to finalize and insert the layer onto your map.

**Manage Layers:**

- You can manage, view, and reorganize your layers from within the Layers tab.
- Simply click and drag the items in the list to alter their visual stacking order.
- Click the eye icon to instantly hide or reveal a specific layer.
- The system fully supports displaying multiple different layers simultaneously.

## [](https://lygos.io/docs/maps/marker-layer)Marker Layer

The Map Marker Layer provides methods to display 3 dimensional spatial data as circular or rectangular markers. These markers scale according to value of the marker and optionally show the value within.

![](https://lygos.io/images/docs/maps/markerLayer_marker-layer-3.png)

### Marker Layer Example Dataset

As an example, consider a dataset tracking capital city populations. This dataset would include:

- **Territory:** The name of the capital city.
- **Latitude:** The geographic latitude coordinate.
- **Longitude:** The geographic longitude coordinate.
- **Population:** The numeric value utilized to determine the size of the marker.

### Getting Started

![](https://lygos.io/images/docs/maps/markerLayer_marker-layer-2.png)

- Load your chosen dataset into the system by following the standard data loading procedures.
- Navigate to the Layouts View and open the Marker Layer settings located within the Settings tab.
- Select the specific data dimension you wish to visualize, such as the Population column.

Once you assign the value dimension, the scaled markers will immediately populate across the map.

### Marker Layer Settings

![](https://lygos.io/images/docs/maps/markerLayer_marker-layer-1.png)

You can extensively customize the behavior and appearance of your markers utilizing the following configuration options:

- **Show Value:** This toggle projects the numeric value as visible text directly on top of the marker.
- **Font Style:** This allows you to select the font family utilized for the displayed value text.
- **Font Color:** This defines the specific color of the value text.
- **Log Scale:** This applies logarithmic scaling algorithms to the marker sizes, where a value of 1 equals no scaling applied.
- **Scale Multiplier:** This setting multiplies the final size result after the logarithmic scaling has been calculated.
- **Is Rectangle:** Enabling this option transforms the default circle markers into rectangles.
- **Border Color:** This allows you to alter the outline color of your markers.
- **Border Width:** This adjusts the pixel thickness of the marker's outline border.
- **Fill Color:** This defines the interior color filling the marker shape.

## [](https://lygos.io/docs/maps/heatmap-layer)Heatmap Layer

The Heatmap Layer translates coordinate based values into color coded gradients to effectively visualize data intensity and concentration across geographic regions.

![](https://lygos.io/images/docs/maps/heatmapLayer_heatmap-layer-2.png)

### Getting Started

- Load your dataset into the software using the standard import steps.
- Navigate to your Layout View and access the Heatmap Layer Settings situated under the Settings tab.
- Within the Dataset configuration section, select a specific Value to drive your heatmap, such as traffic volume, activity levels, or population.

The moment a value is selected, the system will automatically render the Heatmap based on those values and their associated coordinates.

### Heatmap Layer Settings

You can fine tune the behavior and visual style of your heatmap by adjusting the following parameters:

- **Gradient:** Establish a customized color gradient utilizing up to four distinct colors to clearly represent varying levels of intensity.
- **Max:** Determine the maximum point intensity, where higher numerical values generate stronger visual heat points.
- **Min Opacity:** Set the minimum transparency threshold for the heatmap, which is highly useful for crafting subtle data visualizations.
- **Max Zoom:** Define the specific zoom level where the data points reach their absolute maximum intensity, which defaults to the map's overall maximum zoom capability.
- **Radius:** Adjust the specific radius of influence that each individual data point projects onto the heatmap.
- **Blur:** Modify the blur level to sharpen or smooth out the visual transitions bridging different heat areas.

![](https://lygos.io/images/docs/maps/heatmapLayer_heatmap-layer-1.png)

## [](https://lygos.io/docs/maps/geo-json-layer)Geo Json Layer

The GeoJSON Layer can display polygons and markers similar to GeoJSON or KML formats.

![](https://lygos.io/images/docs/maps/geoJsonLayer_geojson-2.png)

### Supported Data Formats

- GeoJSON
- KML

Once your spatial data is successfully loaded into an active layout, the GeoJSON Layer Settings menu will populate under the Settings tab.

### GeoJSON Layer Settings

You can heavily customize the behavior and visual aesthetics of your GeoJSON features utilizing the following options:

![](https://lygos.io/images/docs/maps/geoJsonLayer_geojson-1.png)

- **Stroke:** Toggle the visibility of the stroke. Setting this parameter to false completely removes the borders from your circles or polygons.
- **Color:** This setting dictates the stroke border color.
- **Weight:** This defines the exact width of the stroke measured in pixels.
- **Opacity:** This controls the transparency level of the stroke.
- **LineCap:** This determines the visual shape rendered at the end of a line. Available options include square, round, and butt.
- **LineJoin:** This establishes the shape rendered at the corners where lines intersect. Available options include bevel, round, and miter.
- **Fill:** Toggle the visibility of the fill located inside circles or polygons. Setting this to false disables the inner fill entirely.
- **Fill Color:** This parameter dictates the inner fill color.
- **Fill Opacity:** This setting adjusts the exact transparency of the inner fill.
- **Fill Rule:** This algorithm determines exactly how the interior space of complex shapes is filled, offering nonzero and evenodd options.

### Tips

- Utilize property filters to specifically highlight features based on their underlying data, such as a category or region name.
- For significantly richer geographic visualizations, try combining your GeoJSON layers alongside other distinct layer types.

## [Cluster Layer](https://lygos.io/docs/maps/cluster-layer)

![](https://lygos.io/images/docs/maps/clusterLayer_cluster-layer-2.png)

The Cluster Layer aggregates markers into clusters of markers and display number of markers with a visual gradient.

### Cluster Layer Settings

You can customize exactly how these clustered data points render on your map:

![](https://lygos.io/images/docs/maps/clusterLayer_cluseter-layer-1.png)

- **Icon Size:** Adjust the physical size of the rendered cluster icons.
- **Font:** Modify the font family utilized for the count labels displayed on the markers.
- **Color:** Establish the font color for the marker text.
- **Shape:** Select a specific shape to represent the cluster icon, such as a square or circle.
- **Gradient:** Allocate specific color intervals to visually differentiate clusters based on their total size. The system provides four preset options to help visually distinguish these scale differences.
- **Max Cluster Radius:** Define the maximum pixel radius a cluster is allowed to span outward from its core center. Inputting smaller values will generate more frequent, smaller clusters across the map.
- **Spiderfy Distance Multiplier:** Increasing this numerical value forces the individual markers to space further out when a cluster is clicked and expanded or spiderfied. This is exceptionally useful when deploying large marker icons.
- **Disable Clustering At Zoom:** Establish a strict zoom level threshold where clustering is automatically disabled. Once the user zooms at or past this specific level, the unified clusters break apart and the individual markers render separately.

### Tips

- Deploy clustering functionality for datasets featuring highly dense marker distributions to drastically cut down on visual clutter.
- Combine this tool alongside Marker Layers to simultaneously display detailed individual points and broad cluster overviews depending on the active zoom level.

## [](https://lygos.io/docs/maps/territory-layer)Territory Layer

![](https://lygos.io/images/docs/maps/territoryLayer_territory-layer-2.png)

Territory Layer is a choropleth map where spatial data is administrative regions, such as provinces, states, or countries instead of coordinates. It displays corresponding value for the region through visual color mapping via gradient.

After loading your data into a layout and designating Territory Layer, you can access the Territory Layer Settings menu from the Settings tab.

### How to Visualize Your Data

To activate the Territory Layer:

- Navigate to the Dataset setting.
- Select a specific Value from your data source, which will be utilized to color the regions.
- Choose the correct Region setting based on your data structure:
  - If your dataset utilizes country names, select World.
  - If your dataset utilizes regions or states, select the corresponding country.

Once configured, your data will render across the map regions accordingly.

### Territory Layer Settings

Customize the visual appearance of your territory map utilizing the following options:

![](https://lygos.io/images/docs/maps/territoryLayer_territory-layer-1.png)

- **Region:** This defines the overall scope of your map:
  - World is utilized for country based data.
  - Selected Country is utilized for regional or state data within a specific country.
- **Show Only:**
  - **On** forces the map to only display the regions that exist within your dataset.
  - **Off** forces the map to show all regions, rendering regions that lack data in the default color.
- **Default Color:** This determines the background color applied to regions that are not included in your active dataset.
- **Border Width:** This adjusts the pixel thickness of the borders separating regions.
- **Fill Gradient:** Establish a color gradient utilizing up to four distinct color intervals to represent varying value ranges across the regions.
- **Fill Opacity:** This controls the transparency level of the region fills, where 0 is fully transparent and 1 is fully opaque.

### Tips

- Ensure the region names present in your dataset strictly match standard naming conventions (for example, use "United States", not "USA").
- Utilize the Show Only option to drastically declutter the map when you need to focus on specific regions.

## [](https://lygos.io/docs/maps/icon-layer)Icon Layer

## ![](https://lygos.io/images/docs/maps/iconLayer_icon-layer-3.png)

The Icon Layer displays icon marker for spatial data from an icon collection provided to user. User can either select a general icon for all the markers in the layer or connect a data dimension to icon selection so each data point can determine its own icon dynamically. Moreover, it can display name and value of the data point near icon marker.

### How to Visualize Icon Markers

- Within the Dataset Settings menu, select the Name field.
- This field selection dictates the text label that will render next to each icon.
- Choose your desired Marker Icon from the provided options.

Your icons will immediately render on the map at their corresponding coordinates.

### Example Use Case

As a demonstration, you can visualize capital city populations by utilizing two distinct filters:

- Cities boasting a population over 2 million.
- Cities with a population under 2 million.

You can assign a totally different icon to each filter, and deploy both filters onto the map as separate Icon Layers to create a highly readable visual.

### Icon Layer Settings

You can customize exactly how your icons and their corresponding labels appear:

![](https://lygos.io/images/docs/maps/iconLayer_icon-layer-2.png)

- **Font:** This dictates the font family utilized for the label text.
- **Font Size:** This establishes the pixel size of the label text.
- **Color:** This determines the color of the label text.
- **Stroke Color:** This changes the outline color bordering the text.
- **Stroke Width:** This adjusts the width of the text outline.

### Tips

- Combine your Icon Layers with custom Filters to produce highly detailed visualizations, such as assigning different icons to denote escalating severity thresholds.

## [](https://lygos.io/docs/maps/tracking-layer)Tracking Layer

The Tracking Layer enables users to track vehicles. Users can either from configuration or from data itself determine icon of the vehicle and line options and live or path history data of the vehicle is animated on the screens.

![](https://lygos.io/images/docs/maps/trackingLayer_tracking-map.png)

### Features

- **Live Tracking:** Display the exact current position of your tracked entities in real-time.
- **Path History:** Display the historical route each entity has traveled based on its timestamped coordinates.

### How to Use

- Load your tracking data directly into the layout.
- Your dataset must contain at a minimum:
  - Longitude and Latitude fields to determine position.
  - A timestamp field to accurately order the movement path.
  - A device ID or vehicle ID to properly distinguish between different tracked items.
- The Tracking Layer Settings menu will become available within the Settings tab.
- Configure exactly how the paths and markers render on screen, utilizing custom settings to adjust marker icons, line widths, and line colors.

### Use Case Examples

- Fleet vehicle tracking.
- Delivery route visualization.
- Mobile asset movement history.

## [](https://lygos.io/docs/maps/tile-layer)Tile Layer

The Tile Layer enables administrators to integrate specialized geographic contexts and custom map aesthetics by linking directly to external tile services. This capability is exceptionally valuable when standard base maps fail to provide the cartographic details or specific styling required for your operational environment.

When you need to display highly specialized cartography-such as custom municipal blueprints, topographical data, or high contrast dark mode maps-across a massive operations center video wall, leveraging a dedicated TileSource ensures your foundational map perfectly complements your overlying data.

This feature guarantees an efficient and seamless integration of third party map tiles by providing opacity controls and the ability to disable default base layers to optimize overall rendering performance.

![](https://lygos.io/images/docs/maps/tileLayer_tile-layer-1.png)

### How to Add a Custom Tile Map

- Navigate to the Data Module (not the Data Tab) and select TileSource.
- Input your custom tile service URI.
- After loading your new tile source, assign it directly to your map by adding the TileSource as Data within the Maps Data tab.
- The layer you generate from the tile source will immediately render on your map.
- To avoid performance issues, consider disabling the default base layer from the Base Layers tab. If you do not, the system will continuously fetch and render the default base layer underneath your custom tile layer.

### Tile Layer Settings

- **Opacity:** Adjust the transparency level of your custom tile layer to properly contrast or blend with your other map layers.

![](https://lygos.io/images/docs/maps/tileLayer_tile-layer-2.png)

## [](https://lygos.io/docs/maps/configuration-and-styling)Configuration & Styling

Configuration of the Map Module enables users to determine base and overlay layers and customize existing layers visual settings.

### Base Layers Settings

- **Base Layer:**
  - Select the primary tile layer to function as your base map.
  - You can pick from the built in tile options or import a customized tile layer utilizing the TileSource function.
- **Base Overlay:**
  - This is an optional setting that adds a secondary overlay layer on top of your selected base map.
- **Preset Overlays:**
  - Traffic, Weather (Precipitation, Clouds, Wind, Temperature and Pressure), Graticule and Day Night Cycle on Video Walls.

### Layer Customization

Every individual layer you add to the map can be styled independently. The available customization options will change based on the specific layer type you are working with, such as GeoJSON, Heatmap, or Marker. To edit these settings and styles:

- Select the specific layer you wish to edit from the Layers tab.
- Open the Settings tab.
- Select the Layer and expand its menu.
- Adjust the available properties based on that layer's unique capabilities.

Refer to the documentation for each specific Layer type for detailed breakdowns of configuration options.

## [](https://lygos.io/docs/maps/animating-and-real-time-data)Animating Data & Real-time Data

You can animate your time series data to accurately visualize dynamic changes over time directly on the Map. This functionality is crucial for observing live updates from real-time data sources, tracking movement, or analyzing trends as part of your control room video wall analytics.

### Animation Types

The system provides two distinct animation types, dictated by whether your data source includes time based temporal information:

**1\. Realtime**

- The Map will automatically update whenever there is a data change detected on the connected sources.
- The manual animation controls-such as Loop, Pause, and Play-are completely disabled in this mode.
- Realtime mode is selected automatically if your dataset does not contain a time column.
- If your data does include temporal information, this mode will only display the absolute latest data point.

**2\. Animation**

- This mode can be utilized if your data includes temporal information like timestamps.
- This mode permits the playback of simulated or historical data changes over time.

You can select your preferred Animation type from the Data Input item located within the Settings menu.

![](https://lygos.io/images/docs/maps/animatingAndRealTimeData_animating-1.png)

### Animation Settings

- **Show Label:** This toggle displays the current time of the running animation on the screens.
- **Force Label:** This toggle forces the label to render even if labels have been globally disabled for the active layout.
- **Start / End Time:** This defines the specific time interval the system will animate. The times you input here must match the available time range existing in your dataset.

### Animation Controls

You can thoroughly customize the visual appearance and behavior of your animation:

- You can dictate the total duration of the animation sequence.
- You can utilize the Min Max Window slider to crop the overall duration and strictly limit playback to a specific window.
- You can manually drag the Play slider to instantly seek to a certain point in time within the data.
- The top right of the interface displays the current time within the data sequence.
- The bottom left of the interface houses the AutoPlay, Stop, Pause, and Play buttons.
- The AutoPlay function does not initiate animation within the editors; instead, it automatically starts the animation sequence the moment a layout containing this map is deployed to a screenspace on the video wall.

![](https://lygos.io/images/docs/maps/animatingAndRealTimeData_animating-2.png)

## [](https://lygos.io/docs/maps/deploy-to-screens)Deploy to Screens

Users can deploy to Video wall screens from editor itself by pressing deploy button or use Display Module to deploy to screens of the video wall.

### Editor Deployment Options

**1\. Deploy**

- Select a specific Screenspace to target for your Map Visualization.
- Choose between two placement options:
  - **Add to First Available Space:** This option automatically drops the Visualization into the first empty Layout slot it detects.
  - **Replace Visualization:** This option allows you to select and replace an existing Deployed Visualization. A list of existing deployments is provided for easy selection.

**2\. Assign**

- You can manually Assign the Visualization to a specific Dynamic Slot ranging from 1 to 16.
- Once assigned, these slots can be:
  - Resized
  - Repositioned
  - Replaced
- Utilize the Display Module Layout interface for advanced Dynamic Slot Management.

# [](https://lygos.io/docs/visualization)VISUALIZATION

Lygos Visualization Module offers over 20 different interactive and animated visualization formats for video walls. You can utilize robust logic to implement complex sorting expressions and AND or OR filters. Additionally, you can remotely interact with your data using PC and tablet clients, allowing you to easily explore, animate, and curate real-time data environments that perfectly suit your displays.

### Visualization Types

- **Basic Charts:** Box Plot, Pie, Table, Chart, and Candlestick.
- **Network & Hierarchy:** Sankey, Sunburst, Tree, and Graph.
- **Statistical & Comparison:** Funnel, Polar, and Radar.
- **Heatmaps & Trends:** Multi Line, Parallel Lines, Theme River, and Heatmap.
- **Specialty Charts:** Chart3D, Gauge, Indicator, Tree Map, and Alerts.

### Data Integration

- You can connect data sources as long as they are compatible with your chosen visualization type.
- You can apply sorting logic and filters by utilizing Sort, Filter, OR, and AND expressions.
- You can deeply style and configure display options for your data series and the visualization itself.

### Animation & Real-Time Data

- You can animate time series data.
- You have full control to loop, pause, or play these animations.
- You can watch live data changes stream directly into your visualizations from real-time sources.

### Remote Interaction

- You can manipulate the visualizations on your large video walls utilizing touch gestures or a mouse via your PC and tablet clients.

## [](https://lygos.io/docs/visualization/connect-data)Connect Data

You can seamlessly connect and display information from a variety of data sources that are compatible with your chosen visualization format across your dashboards and video walls.

### How to Use

**1\. Add Data**

- Navigate to the Data & Logic tab within the interface.
- Introduce your new data source here.

**2\. Toggle Data to Visualize**

- Move over to the Datasets & Transform tab.
- Switch the toggle to the ON position for the specific dataset you wish to render.

**3\. Select Visualization Type**

- Pick a visualization format that accurately matches the underlying structure of your data:
  - **Bar Series**
  - **Line Series**
  - **Scatter Series**
- Keep in mind that every visualization format has highly specific configuration options and requirements, so you must ensure your data is a proper match before proceeding.

## [](https://lygos.io/docs/visualization/filter-and-sort)Filter and Sort

You can effortlessly implement sorting rules and filters to refine exactly how your dataset is presented. You can also hide or show these filters whenever necessary to perform deeper data analysis or maintain a cleaner visual layout.

### Sorting

Customize the presentation sequence of your information:

- **Select Dimension:** Pick the specific data field you wish to organize.
- **Select Order:** Decide between a Descending or Ascending order.

### Filtering

Narrow down your dataset utilizing logical conditions:

- **Select Dimension:** Choose the specific data field you want to filter.
- **Add Logical Operators:** Apply specific conditions such as less than, greater than, or equals.
- **Enter Values:** Input the exact values you are filtering your data against.

## [](https://lygos.io/docs/visualization/configuration-and-styling)Configuration & Styling

Users can configure visual and data encoding settings of the visualization series from Configuration and Styling Tab.

### Settings Complexity

You can choose between two primary configuration modes:

- **Simple:** This mode reveals only the most essential settings regarding your data settings and base parameters.
- **Advanced:** This mode unlocks every single available setting for your data settings and base parameters.

### Data Input

- **All:** This renders the complete data series in its entirety.
- **Latest:** This restricts the displayed data points for each specific category. This setting is highly effective for isolating the absolute newest inputs within continuously streaming datasets.
- **Animate/Realtime:** This renders temporal data and permits playback across a timeline. The real-time mode exclusively shows the current data as it continuously updates.

### Base Parameters

You can deeply edit styles and configure specific display options for both the visualization itself and its underlying data series:

- **Color Schemes**
- **Title** style and text content
- **Legend Visibility** (adjusting its position or toggling it on and off)
- **Axes Appearance** (modifying gridlines, ticks, and labels)
- **Text Styles** (customizing the color, size, and font)

## [Visualization Types](https://lygos.io/docs/visualization/visualization-types)

Lygos supports a massive array of data visualization and chart formats. The majority of these formats require you to properly configure your Dataset Settings before they can render on screen.

### Table

![](https://lygos.io/images/docs/visualization-types/table.png)

- This displays your data in a traditional tabular format.
- Features include the ability to filter data, sort columns, and apply style configurations such as borders, colors, and fonts.

### Chart

![](https://lygos.io/images/docs/visualization-types/chart.png)

- This category includes Scatter Series, Line Series, and Bar Series.
- Dataset Settings require an X Axis and a Y Axis.
- Full style customization is available.

### Pie

![](https://lygos.io/images/docs/visualization-types/pie.png)

- This displays your data as a proportional pie chart.
- Dataset Settings require a numerical Value and a category Name.
- Full style customization is available.

### Box Plot

![](https://lygos.io/images/docs/visualization-types/boxplot.png)

- This visualizes data distribution utilizing quartiles.
- Dataset Settings require an X Axis alongside Q0, Q1, Q2, Q3, and Q4 values.
- Full style customization is available.

### Candlestick

![](https://lygos.io/images/docs/visualization-types/candlestick.png)

- This format is commonly utilized for analyzing financial data.
- Dataset Settings require an X Axis alongside Highest, Lowest, Close, and Open values.
- Full style customization is available.

### Graph

![](https://lygos.io/images/docs/visualization-types/graph.png)

- This displays complex nodes and edges.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Tree

![](https://lygos.io/images/docs/visualization-types/tree.png)

- This displays highly hierarchical data structures.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Radar

![](https://lygos.io/images/docs/visualization-types/radar.png)

- This plots your values along radial axes.
- Dataset Settings strictly require a Name.
- Full style customization is available.

### Polar

![](https://lygos.io/images/docs/visualization-types/polar.png)

- This plots your data directly onto circular coordinates.
- Dataset Settings require an Angle and a Radius.
- Full style customization is available.

### Sunburst

![](https://lygos.io/images/docs/visualization-types/sunburst.png)

- This displays hierarchical data using proportional concentric circles.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Heatmap

![](https://lygos.io/images/docs/visualization-types/heatmap.png)

- This visually represents data intensity or density.
- Dataset Settings require an X Axis, a Y Axis, and a Z Axis to represent the intensity value.
- Full style customization is available.

### Sankey

![](https://lygos.io/images/docs/visualization-types/sankey.png)

- This generates a flow diagram to showcase proportional paths.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Funnel

![](https://lygos.io/images/docs/visualization-types/funnel.png)

- This visualizes progression through specific stages.
- Dataset Settings strictly require a Value.
- Full style customization is available.

### Parallel Lines

![](https://lygos.io/images/docs/visualization-types/parallel-line.png)

- This displays complex multi dimensional data comparisons.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Multi Line

![](https://lygos.io/images/docs/visualization-types/multi-line.png)

- This format also displays multi dimensional data comparisons.
- Dataset Settings require an X Axis, a Y Axis, and a Category Dimension.
- Full style customization is available.

### Tree Map

![](https://lygos.io/images/docs/visualization-types/treemap.png)

- This utilizes nested rectangles to visually represent hierarchical proportions.
- It loads immediately and does not require specific dataset settings.
- Full style customization is available.

### Theme River

![](https://lygos.io/images/docs/visualization-types/themeriver.png)

- This showcases trends over a timeline utilizing layered visual streams.
- Dataset Settings require an X Axis, a Y Axis, and a Z Axis.
- Full style customization is available.

### Gauge

![](https://lygos.io/images/docs/visualization-types/gauge.png)

- This generates a circular dial to broadcast a single data value.
- Dataset Settings strictly require a Value.
- Full style customization is available.

### Chart 3D

![](https://lygos.io/images/docs/visualization-types/chart3d.png)

- This provides fully three dimensional charting capabilities.
- Dataset Settings require an X Axis, a Y Axis, and a Z Axis.
- Full style customization is available.

### External Visualizations

- This specialized format displays your existing PowerBI and Tableau reports directly as visualizations.

### Alert

- This allows you to generate custom alerts directly from your datasets.
- You must add data and assign specific data dimensions to act as rules.
- Rule Settings include:
  - **Text**
  - **Type** (Secondary, Primary, Danger, Warning, Info, or Success)
  - **Comparison**
  - **Value**
  - **Timeout**
  - **Sound**
  - **Volume**
- Full style customization is available.

## [](https://lygos.io/docs/visualization/animating-and-real-time-data)Animating & Real-time Data

You can effortlessly animate your time series data to observe dynamic shifts over time directly within your Visualization. This is highly effective for monitoring live updates from real-time sources, tracking movement, or analyzing trends across your dashboards and video walls.

### Animation Types

The system provides two distinct animation types, which are dictated by whether your data includes time based temporal information:

**1\. Realtime**

- The Visualization will automatically update the moment a data change occurs on your connected sources.
- The manual animation controls, including Loop, Pause, and Play, are completely disabled in this mode.
- The Real-time mode is selected automatically if your dataset lacks a time column.
- If your data does include temporal information, this mode will only display the absolute newest data point.

**2\. Animation**

- This mode becomes available if your data contains temporal information, such as timestamps.
- It allows for the complete playback of simulated or historical data changes over a timeline.

You can choose your preferred Animation type from the Data Input item located within the Settings menu.

### Animation Settings

- **Show Label:** This toggle displays the current time of the running animation on your screens.
- **Force Label:** This ensures the label renders even if you have globally disabled labels for the active layout.
- **Start / End Time:** This establishes the precise time interval you wish to animate. The times you input here must match the available time range existing in your dataset.

### Animation Controls

You can thoroughly customize the visual appearance and behavior of your animation sequence:

- You can dictate the overall duration of the animation playback.
- You can utilize the Min Max Window slider to crop the duration and restrict playback to a specific window.
- You can manually drag the Play slider to instantly seek to a specific moment within your data timeline.
- The top right of the interface displays the current time within the data sequence.
- The bottom left of the interface houses the AutoPlay, Stop, Pause, and Play buttons.
- The AutoPlay function does not trigger playback within the editors; instead, it automatically starts the animation the moment the layout is deployed to a screenspace on your dashboards or video wall.

![](https://lygos.io/images/docs/visualization/animatingAndRealTimeData_animating-2.png)

## [](https://lygos.io/docs/visualization/interact-charts-on-screens)Interact Charts on Screens

You can remotely control and interact with the visualizations deployed on your video walls utilizing touch or mouse inputs from your PC or tablet clients through a simplified and unified control dashboard on Management and Control Clients.

### How it Works

- Select the specific Visualization you wish to manipulate from your Client interface.
- Utilize the dedicated controller area provided on your device screen to hover, zoom, or pan across the visualization.
- This capability functions flawlessly across all client devices, including desktop PCs and touch enabled tablets.
- Your mouse or touch events are mirrored instantly on the video wall screens, permitting the dynamic exploration of your data.

## [](https://lygos.io/docs/visualization/deploy-to-screens)Deploy to Screens

You can seamlessly push your customized Visualizations to any Dashboard or Video Wall Screenspace utilizing the Display Module or straight from the Visualization Editor. Simply choose the specific size and layout that aligns with your display strategy. This functionality serves as a flawless bridge connecting your configured data visualizations directly to your physical display hardware.

### Editor Deployment Options

**1\. Deploy**

- Select a specific Screenspace to target for your Visualization.
- Choose between two distinct placement options:
  - **Add to First Available Space:** This option automatically drops the Visualization into the first empty Layout slot it detects on the grid.
  - **Replace Visualization:** This option allows you to select and swap out an existing Deployed Visualization. The system provides a list of existing deployments for easy selection.

**2\. Assign**

- You can manually Assign your Visualization to a specific Dynamic Slot ranging from 1 to 16.
- Once assigned, these dynamic slots can be:
  - Resized
  - Repositioned
  - Replaced
- You can utilize the Display Module Layout interface for advanced Dynamic Slot Management.

# [](https://lygos.io/docs/media)MEDIA

The Media provides 20+ multimedia applications to be deployed to video walls. These applications come with their own editors/viewers. Here are the supported applications and formats:

**Images**

- You can display and upload images onto your screens and video walls.
- You can crop, rotate, and flip your visual assets.
- You can fine tune the saturation, contrast, and brightness.

**Video**

- You can link or upload videos for playback on the video walls.
- The system supports YouTube links, HTML5 videos, and MP4 uploads.
- Playback controls include Loop, Stop, Pause, and Play.

**Documents**

- You can display and upload PDF files.
- Display mode options include Play Once, Loop, or Single Page.
- You can configure specific page visibility durations for the Play Once and Loop modes.

**Diagrams**

- You can construct diagrams utilizing a simple drag and drop interface.
- The tool provides images, BPMN, UML, text, arrows, and shapes.
- You can connect your elements using arrows or lines.

**Gallery**

- You can showcase, manage, and curate dynamic image collections across multi screen setups.
- You can organize tailored galleries using Free or Auto layout modes.
- You can sort your loaded images by Random, Color, Name, Creation Date, or Uploading Date.

**Graphics**

- You can upload GLB files to render 3D objects and scenes.
- You can pilot the camera utilizing a virtual joystick.

**Earth**

- You can render an interactive 3D globe on your video walls.
- You can explore the globe freely utilizing touch or mouse controls.
- You can drop custom GLB models onto specific geographic coordinates.

**Web**

- You can display external web pages, which are converted into static content for security purposes.
- Certain actions and navigations might experience limitations.

**Pages**

- You can import or create rich text documents and HTML pages.
- You can style these pages utilizing tables and images.

**Boards**

- You can display and create Kanban boards.
- Users can edit these boards collaboratively.

**Weather**

- You can broadcast weather data for any chosen location.
- View options include Humidity, Wind, Min Max, Hourly, and Weekly.
- The system utilizes animated backgrounds that match the current weather.

**News**

- You can display and add RSS feeds to your screens.
- These feeds render as customizable cards.
- You can set a specific update frequency.

**Quiz**

- You can display and generate custom quizzes.
- The system utilizes a gamified leaderboard based on user scores.
- Participants join using their mobile devices by scanning a QR code.
- Administrators control quiz progression, including Restart, Show Scoreboard, Show Answers, Show Question, Start, and Show QR.

**Poll**

- You can construct polls for multi screenspace or single screenspace deployments.
- You can configure the voting mode, multiple selection options, and voting security.
- Users cast their votes via QR code on their mobile devices.
- Results can be visualized as a Ranking Chart, Grid, TreeMap, or Pie Chart.

**Calendar**

- You can connect or upload calendars for display on the video walls.
- Supported views include Weekly, Monthly, and Yearly.
- You can edit and add events utilizing local ICS files only.
- You can customize the overall calendar styling.

**Watch**

- You can display timezone, countdown, timer, or clock modes.
- These are controlled via the Control Module or Editor.
- You can customize the style settings.

**Wall**

- You can host a real-time message wall.
- This acts as an internal sharing and chat system for Lygos users.
- Users can post images and messages.

**Messages**

- You can display and connect message streams pulled from APIs.
- You can configure sorting, filtering, and message styles.

**Forex**

- You can display commodities, cryptocurrency, US stocks, and exchange rates.
- You can generate charts or KPI grids.
- The font, color, and background styles are completely customizable.
- Data updates ranging from daily to every 15 minutes depending on your source.

**IPTV**

- You can add M3U streams for display on the screens.
- You have full control over start stop, playback, and volume functions.

**Cast**

- You can cast directly from a management client to the screens.
- You can opt to display content between open tabs or screens.

**Stream**

- You can securely connect RTSP video streams and render them as scalable visualizations.
- You can monitor multiple simultaneous live camera feeds in real-time.
- You can control the video stream volumes.

**WordCloud**

- You can generate and display word clouds on your video walls.
- These can be sourced from custom text, XLSX, PPT, DOCX, or PDF files.
- You can customize the styling.

**Blueprint**

- You can automatically convert DWG CAD files into scalable SVG formats for high fidelity reviews.
- You can adjust Stroke Proportion and Background Color to maximize visibility.

**Deep** **Zoom**

- You can navigate and upload high resolution zoomable images in DWG, SVG, JPEG, PNG, or SZI formats.
- You can seamlessly flip, rotate, pan, and zoom massive files across the X and Y axes.
- You can optimize styling with real-time adjustments for Greyscale, Invert, Gamma, Contrast, and Brightness.

## [](https://lygos.io/docs/media/images)Images

The Images module provides images and photos to be loaded to video walls, users also can edit images on the local editor.

To begin, you must create a new image document using the Management Client. Once created, you import your desired image. This image document is then ready to be deployed to any layout across your screenspaces.

### Import & Export

- **Supported Import Formats:** GIF, BMP, TIFF, PNG, and JPEG.
- **Export Formats:** PNG and JPEG.
- You can manually import the file or use drag and drop.

Note: The system only permits one image per Image document.

### Image Cropping

You can crop your image by physically adjusting the crop area. You have the option to:

- Utilize Free mode for custom cropping.
- Select a fixed aspect ratio such as 4:3 or 16:9.

![](https://lygos.io/images/docs/media/images_images-1.png)

### Image Controls

- **Zoom:** Magnify or shrink the image view.
- **Move:** Shift the image utilizing the arrow buttons.
- **Rotate:** Turn the image 90 degrees right or left.
- **Flip:** Mirror the image vertically or horizontally.
- **Fullscreen:** Expand the image to full view.
- **Adjust:** Fine tune the saturation and brightness.

### Display Modes

These settings dictate exactly how the image renders on the deployed screens:

- **Stretch:** This forces the image to fill its container entirely, which may distort the aspect ratio.
- **Fit:** This fits the image entirely inside the container while maintaining its original aspect ratio.
- **Fill:** This fills the entire container but crops portions of the image to preserve the aspect ratio.

![](https://lygos.io/images/docs/media/images_images-2.png)

### Deploy on video walls and Dashboards

You can deploy directly through the Image Editor by pressing Deploy. Simply choose a screenspace and select whether to swap it with an active visualization or load it into the first available slot. Alternatively, you can deploy via the Display Module. Navigate to the Display Module, select your desired layout and screenspace, then choose your visualization and drag and drop it into the grid area.

## [](https://lygos.io/docs/media/video)Video

The Video module enables you to play MP4 files, HTML5 or Youtube videos on your video wall.

To begin, create a new video document within the Management Client. Link or import your video to this document, and it becomes ready for deployment to any layout.

### Video Types

- **File:** Upload your local MP4 files. Export and import are fully supported.
- **HTML5:** Provide a link to online WEBM or MP4 videos.
- **YouTube:** Embed a YouTube video utilizing its URL.

![](https://lygos.io/images/docs/media/video_video-1.png)

### Video Controls

Once your video is added, you can manipulate the following controls:

- **Progress Bar:** This displays the total duration and the current time of the video.
- **Crop Slider:** You can trim the video duration by moving the start and end points on this secondary slider.
- **Playback Controls:** Includes Rewind, Fast Forward, Stop, Pause, and Start.
- **Loop Toggle:** Enable this to force the video to loop continuously.
- **Volume Control:** Toggle the mute function or manually adjust the volume.
- **Show Label:** This visually displays the video duration and current time on the deployed screen.

![](https://lygos.io/images/docs/media/video_video-2.png)

Important: These controls remain synchronous across all clients, meaning your adjustments will directly affect the video currently playing on the video wall.

### Deploy on video walls and Dashboards

Deploy directly from the Editor by clicking Deploy, picking your screenspace, and choosing to either load into an empty spot or swap with an active visualization. You can also deploy utilizing the Display Module. Navigate to the Display Module, pick your layout and screenspace, then drag and drop your selected visualization into the grid.

## [](https://lygos.io/docs/media/documents)Documents

The Documents module allows you to display PDF documents on video walls.

### Upload

- **Supported Format:** PDF.
- You can import your files via the file picker or simply drag and drop them.

### Display Modes

You can dictate exactly how the PDF renders on your screens:

- **Single:** This displays one selected page. You utilize the right and left arrows to select which page to show.
- **Play:** This automatically cycles through every page in sequence exactly one time. You must specify the duration per page in seconds.
- **Loop:** This cycles through the document pages continuously. You must specify the duration per page in seconds.

![](https://lygos.io/images/docs/media/documents_documents-1.png)

### Document Controls

Utilizing the Control interface, you can:

- **Zoom In / Zoom Out:** Magnify or shrink the document view.
- **Rotate:** Spin the document to a different orientation.

### Deploy on video walls and Dashboards

You can deploy through the Editor by pressing Deploy, choosing your screenspace, and selecting whether to swap it with an existing visualization or drop it into the first open spot. You can also utilize the Display Module by navigating to it, picking your screenspace and layout, and then dragging your chosen visualization into the grid.

## [](https://lygos.io/docs/media/diagrams)Diagrams

The Diagrams module allows you to create basic diagrams from local diagram editor and display it at video walls.

### Insert Shapes

- Shapes are organized into specific Shape Libraries, such as network, flowchart, or basic.
- You can collapse or expand these libraries by clicking on their names.
- To place a shape, you can either drag and drop it onto your canvas, or simply click it to insert.

### Format Panel

Positioned on the right side of the screen, the Format Panel is context sensitive, adapting its options based on what element you currently have selected:

- **Style shapes:** Adjust shadows, borders, and fill colors.
- **Connectors:** Modify routing options, arrows, and line types.
- **Text:** Change the alignment, size, and font.
- **Layout:** Alter the layering, rotation, size, and position.

### Export Options

You can export your completed diagram in two formats:

- **PNG:** Ideal for utilizing the diagram as an image within presentations or reports.
- **SVG:** Ideal for retaining editable, scalable vector graphics.

### Deploy on video walls and Dashboards

Deploy directly from the Editor by clicking Deploy, selecting a screenspace, and choosing to either load into an empty slot or swap out a live visualization. You can also deploy via the Display Module by navigating there, selecting your layout and screenspace, and dragging the visualization into the active grid.

## [](https://lygos.io/docs/media/gallery)Gallery

The Gallery module enables users to deploy gallery of images as a grid to video walls.

### Importing Images

- You can import files directly or use drag and drop.
- Your uploaded images will populate in the Images tab.
- These imported images are not automatically displayed on your screens.

To push the images to your displays:

- Highlight the selected images and press Load.
- The loaded assets will then render on the deployed screens.

From within the Images tab, you have the ability to:

- **Delete** images
- **Preview** images
- **Export** images

### Mode

You can define exactly how your images arrange themselves inside the deployed layout:

- **Auto:** The system automatically arranges and sizes the images to optimally fill the layout space.
- **Free:** You can manually arrange the images, giving you control over image sizes, the gaps between images, and the specific image order.

### Sorting Options

You can sort your loaded images by:

- Uploading Date
- Creation Date
- Name
- Color
- Random

### Deploy on video walls and Dashboards

Deploy directly via the Editor by clicking Deploy, choosing your screenspace, and picking whether to fill an open spot or swap with an existing visual. You can also deploy using the Display Module by selecting your layout and screenspace, then dragging the visualization into the grid area.

## [](https://lygos.io/docs/media/graphics)Graphics

The Graphics module enables to display 3D interactive scenes on video walls in format of GLB.

### Import / Export Format

- **Supported Format:** .glb (The binary version of gLTF).
- **About GLB:** This is an open source format designed for 3D models and scenes. It encapsulates every asset, including animations, textures, and meshes, directly into a single binary file. Because it requires no external files, it is highly efficient and portable.

![](https://lygos.io/images/docs/media/graphics_graphics-1.png)

### How to Use

- **Import** your .glb file into the system.
- **Customize** the environment utilizing the settings panel on the right side:
  - **Camera Settings**
  - **Lighting Options**
  - **Scene Configurations**

### Deploy on video walls and Dashboards

You can deploy from the Editor by pressing Deploy, picking your screenspace, and deciding to either swap out an active visualization or drop it into the first empty spot. Alternatively, utilize the Display Module to select your layout and screenspace, then drag and drop the visualization directly into the grid.

## [](https://lygos.io/docs/media/earth)Earth

The Earth module delivers an interactive, powerful 3D globe designed for geospatial data representation and comprehensive visual exploration.

### Features

- You can interact with and navigate the 3D Earth map freely.
- You can customize your perspective by altering the Overlay Layers and Base Tile Layers.
- You can place and import your custom 3D Models (.glb files) straight onto the Earth view.

![](https://lygos.io/images/docs/media/earth_earth-1.png)

### Size Restrictions

- The Earth element carries a strict maximum layout size of 3 screens high by 3 screens wide.

![](https://lygos.io/images/docs/media/earth_earth-2.png)

### Deploy on video walls and Dashboards

Deploy directly from the Editor by clicking Deploy, choosing a screenspace, and selecting whether to load into the first open slot or swap with an active visual. You can also deploy via the Display Module by picking your screenspace and layout, then dragging your visualization into the grid area.

## [](https://lygos.io/docs/media/web)Web

The Web module enables you to embed and display external websites directly on video walls.

### How to Use

- Type your required web URL into the designated input field.
- Press the tick icon to process and display the web page on your layout.

### Features

- This module supports live web page viewing.
- It is perfect for displaying embeddable web content, news feeds, reports, or external dashboards.

### Limitations

- To ensure security, Web Pages are converted into Static Sources before rendering on screen. This conversion process may introduce limitations to the page's standard navigation and functionality.

### Deploy on video walls and Dashboards

Deploy directly through the Editor by pressing Deploy, choosing a screenspace, and deciding to load into an available spot or swap out a current visualization. You can also deploy utilizing the Display Module by selecting your layout and screenspace, and dragging the visualization into the grid.

## [](https://lygos.io/docs/media/page)Page

The Page module provides a built in rich text editor for constructing custom HTML information pages to be displayed on video walls.

### Import and Export Types

- **Supported Format:** HTML.

![](https://lygos.io/images/docs/media/page_page-1.png)

### Editor Features

- **Text Formatting:** Utilize headings, paragraphs, horizontal lines, and block quotes.
- **Font Modes:** Apply strikethrough, underline, italic, bold, superscript, and subscript formatting.
- **Font Settings:** Adjust the background color, font color, font family, and font size.
- **Alignment:** Align your text to the right, center, or left.
- **Lists and Structure:** Create numbered lists, bulleted lists, and to do lists with clickable checkboxes.
- **Indentation:** Control text indentation for better structure.
- **Advanced Elements:** Insert interactive tables, code snippets, full code blocks, and draggable images.
- **Utilities:** Utilize undo and redo functions, find and replace, set custom background colors, and directly edit the HTML source code.

**Important Note:** You must avoid uploading excessively large image files, as the system enforces a strict file size limit for image uploads.

### Deploy on Video Walls and Dashboards

- You can deploy straight from the Editor by clicking Deploy, selecting a screenspace, and choosing to either load into the first available spot or swap out an active visualization.
- Alternatively, navigate to the Display Module, select your layout and screenspace, and drag and drop the visualization directly into the grid area.

## [](https://lygos.io/docs/media/boards)Boards

The Boards module enables you to seamlessly manage and integrate interactive Kanban style task boards into your display environment.

### Import and Export Types

- **Export from Trello:** Open your Trello Board, navigate through Menu to More, select Print & Export, click Export as JSON, and save the file to your device.
- **Import to Lygos:** Go to Import and upload your saved Trello JSON file.
- **Lygos Board JSON Format:** You can export and import directly utilizing Lygos' native JSON structure.

![](https://lygos.io/images/docs/media/boards_boards-1.png)

### Board Features

- **Drag & Drop:** You can move tasks between different lists and freely reorder the lists themselves utilizing drag and drop support.
- **Customization:** You can visually style your Kanban board to perfectly match your brand or personal preferences.

![](https://lygos.io/images/docs/media/boards_boards-2.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by pressing Deploy, choosing a screenspace, and selecting whether to swap with a deployed visualization or load into an empty slot.
- You can also deploy via the Display Module by selecting your screenspace and layout, then dragging your visualization into the active grid.

## [](https://lygos.io/docs/media/weather)Weather

The Weather module allows you to integrate dynamic forecasts and real-time meteorological data onto your displays.

### Location and Frequency

- **Location:** Enter the specific location you wish to monitor, which can be changed at any time.

![](https://lygos.io/images/docs/media/weather_weather-1.png)

- **Update Frequency:** Establish exactly how often the weather data should refresh, such as hourly or every 15 minutes.

![](https://lygos.io/images/docs/media/weather_weather-2.png)

### Display Settings

- **Temp Scale:** Choose between Fahrenheit and Celsius.
- **Icon Set:** Select distinct icon styles to represent weather indicators.
- **Background Images:** Toggle animated background visuals, noting that this only functions when your layout size is equal to or smaller than the screen.
- **Background Color:** Establish a solid background color to be utilized when background images are disabled.
- **Text Color & Font:** Customize the text color and font style.

![](https://lygos.io/images/docs/media/weather_weather-3.png)

### Visibility Options

- **Weekly View:** Displays the weather forecast for the upcoming six days.
- **Weekly Min/Max:** Displays the maximum and minimum temperatures when the Weekly View is active.
- **Hourly View:** Displays the forecast broken down into three hour intervals.
- **Hourly Data Toggles:** Show or hide specific hourly data points, including Humidity, Wind, and Temperature.

### Deploy on Video Walls and Dashboards

- Deploy directly through the Editor by clicking Deploy, picking a screenspace, and choosing to swap with a current visual or load into the first open spot.
- Alternatively, utilize the Display Module to select your layout and screenspace before dragging the visualization into the grid.

## [](https://lygos.io/docs/media/news)News

The News module provides a streamlined method for integrating external updates and live information feeds into your workspace..

### Add RSS Feed

- **Step 1:** Enter your target RSS Feed URL into the provided input field.
- **Step 2:** Click the Confirm checkmark button.
- **Step 3:** The news items from your selected feed will immediately render in the view.

### Customize View

- You can adjust the visual style to dictate exactly how your news feed renders on screen.
- You can personalize the colors, layout, and fonts to perfectly match your overall screen design.

![](https://lygos.io/images/docs/media/news_news-1.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, selecting a target screenspace, and deciding to either load into an available spot or swap out a deployed visualization.
- You can also deploy via the Display Module by picking your screenspace and layout, then dragging the visual into the grid area.

## [](https://lygos.io/docs/media/quiz)Quiz

The Quiz module empowers you to host and build interactive, real-time trivia games. Featuring a gamified leaderboard, an intuitive question editor, and comprehensive host controls, players can seamlessly join and compete directly from their mobile devices.

### Quiz Editor

- **Quiz Creator:** Utilize this to compose your questions and answer choices.
- **Settings Panel:** Utilize this to customize the appearance and behavior of the quiz.
- **Add a Question:** Type your question, provide four answer options, and select the correct one.
- **Images:** You can optionally upload an image to accompany the question, and utilize the Remove Image button to delete it if necessary.
- **Navigation:** Click Next to generate a new question, utilize Previous and Next to browse your list, or press Delete to remove a question entirely.

![](https://lygos.io/images/docs/media/quiz_quiz-1.png)

### Style Settings and Usernames

- **Customize:** Adjust the Font Family, Font Color, and Background Color.
- **Question Time:** Establish exactly how many seconds players have to lock in their answers, keeping in mind that faster answers yield more points.
- **Usernames:** The system automatically generates random usernames, which appear on the scoreboard between rounds.

![](https://lygos.io/images/docs/media/quiz_quiz-2.png)

### How to Play

- **Step 1:** Create and deploy your finished quiz to an active Layout.
- **Step 2:** The host opens the Control interface and clicks Show QR.
- **Step 3:** Players scan the QR code with their mobile devices to access the quiz website.
- **Step 4:** Players select their avatar and username.
- **Step 5:** The host clicks Start Quiz once everyone has successfully joined.
- **Step 6:** Players view the questions on the video wall and submit their answers from their devices before the countdown timer expires. Submitted answers cannot be changed.

### Control Quiz Flow

- **Show QR:** Displays the joining QR code alongside the current player count.
- **Start Quiz:** Renders the first question and initiates the countdown timer.
- **Number of Answers:** Reveals exactly how many players selected each available option.
- **Correct Answer:** Highlights the correct option on the screen.
- **Show Scoreboard:** Displays the current player scores after a question concludes.
- **Show Leaderboard:** Displays the top three players after the final question.
- **Restart Quiz:** Completely resets the Control cycle.

## [](https://lygos.io/docs/media/poll)Poll

The Poll module enables you to gather real-time audience feedback by creating interactive surveys. Featuring dynamic live result visualizations and robust voting security, users can securely cast their votes via QR code on their mobile devices.

### Poll Editor

- **Step 1:** Enter your primary poll question.
- **Step 2:** Input up to eight different answer options.
- **Step 3:** You can optionally upload an image to visually accompany your poll.

![](https://lygos.io/images/docs/media/poll_poll-1.png)

### Style Customization

- **Background Color:** Establish the background color for the deployed screens.
- **Font Color:** Modify the text color to ensure optimal visibility.
- **Font:** Select a specific font style for your poll.

### Settings

- **Voting Security - Session:** This allows one vote per active browser session, though it is susceptible to voter manipulation.
- **Voting Security - Token:** This forces voters to utilize a secure, one time token.
- **Voting Security - Show Tokens:** Click this within the editor to generate, copy, and distribute the tokens.
- **Multiple Selection:** Enable this setting to permit voters to select multiple options simultaneously.
- **Mode - Per Layout:** Controls inside the Editor are disabled, meaning the same Poll Visualizations deployed on different Screenspace Layouts must be controlled separately.
- **Mode - Everywhere:** Poll behavior remains perfectly synced across all Screenspace Layouts and is controlled exclusively from the Editor.

### Poll Controls and Result Types

- **Show QR:** Displays the QR code for users to scan, which is the default view upon deployment.
- **Result:** Displays your selected result type with live, animated updates.
- **QR and Result:** Displays both the live results and the joining QR code simultaneously.
- **Result Types:** Choose between a Pie Chart, Treemap, Grid, or Ranking visualization to display your live results.

![](https://lygos.io/images/docs/media/poll_poll-2.png)

### Deploy on Video Walls and Dashboards

- Deploy through the Editor by pressing Deploy, picking a screenspace, and selecting whether to fill an open spot or replace a current visualization.
- You can also deploy utilizing the Display Module by selecting your screenspace and layout, then dragging the visualization into the grid.

## [](https://lygos.io/docs/media/calendar)Calendar

The Calendar module allows you to integrate and manage timelines, events, and schedules directly on your displays. Supporting both auto refreshing remote feeds and interactive local files, this tool guarantees your team stays perfectly aligned.

### Import and Export Formats

- **ICS:** The standard iCalendar format.
- **JSON:** A custom JSON calendar format.

![](https://lygos.io/images/docs/media/calendar_calendar-1.png)

### Local Calendars

- **Storage:** These are stored locally within your system.
- **Management:** You have full support to delete, edit, and add events.
- **Display Views:** You can switch between List, Week, Month, and Year views.
- **Importing:** You can import standard ICS files to instantly populate the calendar with events.
- **Customization:** You can deeply customize the colors and styles to tailor the display.

![](https://lygos.io/images/docs/media/calendar_calendar-2.png)

### Remote Calendars

- **Storage:** These are stored on external platforms, such as Outlook or Google Calendar.
- **Management:** These are strictly view-only inside Lygos, meaning no editing is permitted from within the system.
- **Data Fetching:** The system always fetches the absolute latest data each time the calendar is displayed.
- **To Add:** Paste the remote calendar URL and press the check button to load it.

**Important Note:** If you execute changes on the external platform while the remote calendar is actively displayed, you must refresh the editor or the visualization to force the updates to appear.

![](https://lygos.io/images/docs/media/calendar_calendar-3.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, choosing a screenspace, and selecting whether to drop into an empty slot or swap with an active visual.
- Alternatively, utilize the Display Module to select your layout and screenspace, then drag and drop the visualization into the grid.

## [](https://lygos.io/docs/media/watch)Watch

The Watch module delivers essential synchronization and timekeeping tools directly to your dashboards and video walls. Offering five distinct modes and extensive visual customization, this tool ensures your operations remain perfectly on schedule.

### Modes

- **Clock:** Displays the current date and time.
- **Timer:** Functions as a countdown timer featuring reset, stop, and start controls.
- **Count:** Functions as a stopwatch counting upwards from zero, featuring reset, stop, and start controls.
- **Animation:** Syncs perfectly with visual animations running across your screens.
- **Timezone:** Displays multiple different clocks tracking various time zones within a single unified view.

![](https://lygos.io/images/docs/media/watch_watch-1.png)

### Style Settings

- **Customization:** You can adjust the Font Size, Font Type, Foreground Color, and Background Color.
- **Toggles:** You can toggle the display of Milliseconds/Seconds, as well as the Date/Time Zone display (restricted to Clock mode only).

![](https://lygos.io/images/docs/media/watch_watch-2.png)

### Animation and Timezone Mode Details

- **Animation Mode:** Renders a synchronized animation clock, which is crucial for visually representing sync timing across animations. You must sync your visualizations from the Layout Tab within the Control Module.
- **Timezone Mode:** Allows you to add and display multiple distinct clocks from different time zones, making it ideal for tracking global events.

### Deploy on Video Walls and Dashboards

- Deploy directly through the Editor by pressing Deploy, picking a screenspace, and deciding to either load into an available spot or swap out a deployed visual.
- You can also deploy via the Display Module by selecting your screenspace and layout, then dragging your visualization into the grid area.

## [](https://lygos.io/docs/media/wall)Wall

The Wall module provides a real-time, centralized messaging system that facilitates seamless communication across your Lygos environment. By generating QR codes or user specific links, your team can securely join the chat from their mobile devices to share images, voice notes, and rich text messages.

![](https://lygos.io/images/docs/media/wall_wall-2-1.jpg)

### Messaging Features

- **Capabilities:** Every connected user has the ability to transmit images, voice messages, and text messages.
- **Rich Text:** Text messages fully support rich formatting, including strikethrough, underline, italics, and bold text.
- **Attachments:** You can easily attach GIFs and images to enrich your communications.
- **Real-time:** All messages render in real-time on the deployed display screens.

### Creating/Managing Wall Users

Additional users can be created from Users Tab in addition to Existing Master Keys and Users Keys. These Users can connect via link or QR and join the team chat that displays live on the video wall by Text, Image or Voice Recording.

### Display Behavior

![](https://lygos.io/images/docs/media/wall_wall-1-1.jpg)

- **Visibility:** New messages automatically populate within the visible area of the message wall.
- **Scrolling:** You can freely scroll within the editor to view older, previous messages.
- **Deletion:** You can delete messages from the editor by clicking the 'X' icon located at the top of every individual message.

### Style Options

- **Customization:** You can deeply customize the message wall's appearance by adjusting the Default Font Color, Title Font, Title Color, Border Size, Border Color, and Background Color.

![](https://lygos.io/images/docs/media/wall_wall-3.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, selecting a target screenspace, and choosing to swap with an active visualization or drop into the first empty spot.
- You can also deploy via the Display Module by picking your screenspace and layout, then dragging the visual into the grid area.

## [](https://lygos.io/docs/media/messages)Messages

The Messages module enables you to seamlessly monitor and integrate live, data driven feeds of communications, events, or alerts directly into your environment. Whether you are streaming real-time operational updates across a massive video wall or tracking critical system notifications in a security operations center, this tool guarantees your team never misses a crucial event. Because it dynamically pairs with external or internal data sources, it features customizable styling, timestamp controls, and robust logical filtering to perfectly tailor your information streams.

**Important Note:** This is the only Media Visualization within the Lygos platform that strictly requires a connected data source in order to function.

### Data & Logic

- You must first load your message data source, which can be an internal feed, an API, or a JSON file.
- Once successfully loaded, the messages will render dynamically on screen as they arrive.

### Style Options

You can thoroughly customize the visual appearance of your message feed:

- **Border Color**
- **Background Color**
- **Font Color**
- **Font Type**
- **Show Time:** Toggle the visible timestamps on or off.
- **Scale:** Manually adjust the visual scale of the feed elements.

![](https://lygos.io/images/docs/media/messages_messages-1.png)

### Filters

You can refine exactly what content renders on screen utilizing the following filter options:

- **Window Size:** Define the exact number of messages that are visible simultaneously.
- **Title Filter:** Force the system to only show messages matching specific titles.
- **Tags Filter:** Filter your messages utilizing tags, which supports complex logical expressions for advanced filtering requirements.
- **Location Filter:** Force the system to only display messages related to a defined geographic location.

![](https://lygos.io/images/docs/media/messages_messages-2.png)

### Deploy on Video Walls and Dashboards

- Deploy directly from the Editor by clicking Deploy, selecting a screenspace, and choosing whether to swap with a live visualization or load into the first available slot.
- Alternatively, utilize the Display Module to pick your screenspace and layout, then drag the visualization into the grid area.

## [](https://lygos.io/docs/media/forex)Forex

The Forex module enables you to visualize and track live financial market data directly inside your workspace.

### Getting Started

- Utilize the Search bar to locate and select your required trading pairs.
- You can opt to display your selected pair as either the Current Price or a Line Chart.

![](https://lygos.io/images/docs/media/forex_forex-1.png)

### Layout & Cards

- Your added pairs will appear visually as cards within the grid area.
- You can resize and place these cards based entirely on your active screen Layout.
- For example, if your current layout is 4x4, scaling a card to 4x4 within the Forex editor will force it to fill the entire screen.

### Time Span Selection

You can adjust the displayed timeframe using the controls in the top left corner of each card:

- **Current** (This displays the Live Price)
- **Day**
- **Week**
- **Month**

![](https://lygos.io/images/docs/media/forex_forex-2.png)

### Style Customization

Personalize your financial display utilizing these options:

- **Background Color**
- **Border Color & Size**
- **Font & Font Color**
- **Chart Type:** Toggle between an Area chart or a Line chart.
- **Area Color:** Defines the background color utilized for area charts.
- **Axis Color:** Defines the color of the line strokes and axes within the charts.

![](https://lygos.io/images/docs/media/forex_forex-3.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, choosing a screenspace, and deciding to either replace an active visualization or drop into an open spot.
- You can also deploy via the Display Module by selecting your layout and screenspace, then dragging the visual into the grid.

## [](https://lygos.io/docs/media/ip-tv)IPTV

The IPTV module enables streaming live television and continuous video feeds into your environment.

### How to Use

- Paste your standard IPTV link directly into the provided input field.
- Click the Play button to initiate the stream.
- The stream will immediately begin playing on your Deployed Screens and within the Editor.

### Controls & Behavior

- Once initiated, IPTV streams cannot be stopped or paused.
- Mute options and Volume Control are available.
- Please note that volume controls will only function on the actual display devices, and do not function within the Editor interface.

![](https://lygos.io/images/docs/media/ipTv_iptv-1.png)

### Deploy on Video Walls and Dashboards

- Deploy directly through the Editor by pressing Deploy, picking a screenspace, and selecting whether to fill an empty spot or swap out a live visualization.
- Alternatively, utilize the Display Module to select your layout and screenspace, then drag the visualization into the active grid.

## [](https://lygos.io/docs/media/cast)Cast

The Cast module allows you to securely share live screens from remote or local computers directly into your display environment.

### Connection Setup

- Every user attempting to cast must be connected to the exact same server.
- One user must initiate the process by starting the server in Local Mode.
- Subsequent users must join the server in Remote Mode, which requires them to enter the server user's password and IP address.

### How to Start Casting

- The moment you initiate a screen cast, your computer populates in the Castable Devices list within the system.
- As the cast creator, click your newly created cast to view your screen within the editor.
- Select the specific tab or screen you wish to broadcast from the available sources list.
- If you opened a new tab or cannot see your desired source, simply click Refresh Sources.
- Other connected users will see your cast populated under their Screen Casting list. They can click it to view your live screen.

### Managing Casts

- To completely remove an active cast, navigate to the Screen Casting list, click Edit Visualization, and then press Delete.

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, selecting a target screenspace, and choosing to swap with a deployed visualization or load into an empty slot.
- You can also deploy via the Display Module by picking your screenspace and layout, then dragging the cast visual into the grid area.

## [](https://lygos.io/docs/media/stream)Stream

The Stream module delivers a highly scalable, secure solution for integrating live RTSP camera feeds directly into your workspace.

![](https://lygos.io/images/docs/media/stream_stream-editor.png)

### Deploy on Video Walls and Dashboards

- Deploy directly through the Editor by pressing Deploy, choosing a screenspace, and deciding to either load into an available spot or replace a live visualization.
- Alternatively, utilize the Display Module to pick your screenspace and layout, then drag and drop the stream visualization into the grid.

## [](https://lygos.io/docs/media/wordcloud)Wordcloud

The Wordcloud module offers a dynamic method for analyzing and visualizing massive volumes of text data directly on your displays. Whether you are highlighting critical operational themes across a video wall or identifying core trends during a briefing, this tool instantly transforms pasted text and raw documents into impactful visual summaries. Featuring support for multiple file formats, vibrant color schemes, dynamic rotation, and intuitive data editing to manipulate word frequencies, you can effortlessly construct compelling text visualizations.

![](https://lygos.io/images/docs/media/wordcloud_wordcloud-1.png)

### Data Input

- **Import Documents:** You can upload documents in .xlsx, .ppt, .docx, and .pdf formats.
- **Paste Text:** You can directly paste or type any text into the system.
- Once your text content is processed, the generated words will populate under the Data tab.

### Data Tab

- You can edit and view individual words within this tab.
- You can manually adjust the visual sizes of specific words. Note that the default sizing is applied based strictly on frequency ratios.

### Config Tab - Style Customization

You can thoroughly customize your wordcloud utilizing these options:

- **Background Color**
- **Font Type**
- **Random Colors:** Disable or enable the use of random font colors.
- **Font Color:** Used to define a specific color if the random colors toggle is disabled.
- **Rotation:** Control the exact rotation and angle of the rendered words.
- **Padding:** Establish the visual spacing between the individual words.

![](https://lygos.io/images/docs/media/wordcloud_wordcloud-2.png)

![](https://lygos.io/images/docs/media/wordcloud_wordcloud-3.png)

### Deploy on Video Walls and Dashboards

- Deploy from the Editor by clicking Deploy, choosing a screenspace, and selecting whether to fill an open spot or swap out a live visualization.
- You can also deploy via the Display Module by selecting your layout and screenspace, then dragging the visual into the grid area.

## [](https://lygos.io/docs/media/blueprint)Blueprint

The Blueprint module enables importing and displaying CAD files on video walls.

### Supported File Formats

- **Import Types:** DWG Files.
- **Export Types:** SVG, PNG.

### Styling Options

You can heavily edit the representation stylings to maximize readability based on your display requirements:

- **Background Color:** Modify the background to match your overall display theme or increase contrast.
- **Stroke Proportion:** Adjust the physical line thickness of the technical drawing to guarantee it remains highly visible at varying viewing distances and scales.

### Deploy on Video Walls and Dashboards

You can quickly deploy your blueprints straight from the editor:

**1\. Deploy** Select the specific screenspace where you want to render the drawing. Selecting a screenspace will instantly list all currently deployed visualizations on the right side of your interface.

- **Add to First Available Spot:** Deploy the CAD blueprint directly into the first empty slot on the grid.
- **Replace Visualization:** Deploy the blueprint by actively replacing a slot or visualization that is already active on the layout.

**2\. Assign** Assign your CAD blueprint to a designated dynamic slot for flexible future deployment.

- You can assign the drawing to an already loaded slot, or to a slot that does not currently exist on the layout grid. The moment that specific slot is loaded onto a screen, the assigned blueprint will immediately render.
- Slots can be deployed to Layouts via the Assign Category located on the Display Module.

## [](https://lygos.io/docs/media/deep-zoom)Deep Zoom

Deep Zoom enables loading Giga Pixel images in various formats to Video walls and enables users to interact with it.

### Supported File Formats

- **Import Types:** DWG, SVG, JPEG, PNG, and SZI.
- **Export Types:** SZI.

### Image Controls & Adjustments

You have total control over the styling of your high resolution images utilizing the built in tools:

- **Navigation:** Smoothly pan the image along both the Y and X axes, and zoom in or out freely.
- **Orientation:** Flip the image horizontally or rotate it entirely.
- **Fit Options:** Force the image to fit the display entirely within the frame, horizontally, or vertically.
- **Visual Styling:**
  - Increase or decrease the Gamma, Contrast, and Brightness levels to achieve optimal visibility.
  - Toggle the Invert setting to completely reverse the image colors.
  - Toggle the Greyscale setting to strip color and view the image in black and white.

### Deploy on Video Walls and Dashboards

You can easily deploy your high resolution images directly from the editor:

**1\. Deploy** Select the specific target screenspace. Selecting a screenspace will list all of the currently deployed visualizations on the right side of the screen.

- **Add to First Available Spot:** Drops the image directly into the first open slot on the layout grid.
- **Replace Visualization:** Deploys the image by overriding a slot or visualization currently active on the layout.

**2\. Assign** Assign your Deep Zoom asset to a specific dynamic slot.

- You can assign the image to an active slot, or to a slot that has not yet been placed on the layout grid. Once that slot is pushed to a screen, the assigned image will appear instantly.
- Slots can be easily deployed to Layouts from the Assign Category inside the Display Module.

# [](https://lygos.io/docs/signage)SIGNAGE

The Signage module allows you to loop or schedule signage content to video walls. These content can be any map, visualizations or media within Lygos environment.

**Key Features**

- You can incorporate any available type of visualization directly into your signage loops.
- The interface allows you to drag and reorder elements to build a customized playback sequence.
- Users can assign a highly specific custom duration to every individual visualization.
- You have the ability to preview the entire loop before pushing it live to your displays.
- You can deploy these finished loops to your dashboards and video walls to achieve automated, continuous playback.

## [](https://lygos.io/docs/signage/add-visualizations)Add Visualizations

You can integrate absolutely all types of visual content into your Signage Loops on your dashboards and video walls, including Visualization Elements, Media, Sensor Data, and Maps.

### How to Add Visualizations

- **Select Visualization Type**
  - Choose from your available categories, such as Media, Sensors, or Maps.
- **Add Visualization Element**
  - Click the Add button located directly next to your chosen Visualization Element to insert it into your active signage loop.

Utilizing this method generates highly engaging and dynamic screen content that automatically cycles through your various visualization formats.

![](https://lygos.io/images/docs/signage/addVisualizations_add-visualizations-1.png)

## [](https://lygos.io/docs/signage/configure-loop)Configure Loop/Schedule

To begin configuring schedules or signage loops for your video walls, you must first create them within the Signage module. After creation, add your desired visualizations-like charts, media, and maps-to the schedule or loop. Once added, these elements will populate in a dedicated list on the right side of your screen.

### For Schedules

- You must input a specific trigger time for every visualization you add.
- Once configured, these scheduled visualizations will automatically trigger at your exact defined time every single day.

### For Loops

- Click the clock icon located on each visualization to define exactly how many seconds that specific element will remain visible on screen during the playback loop.

### Arrange Order

- You can easily drag and drop your visualizations to reorder them and establish your perfect playback sequence.

This configuration process empowers you to create entirely custom loops that cycle through diverse content at your preferred pace across your dashboards and video walls.

![](https://lygos.io/images/docs/signage/configureLoop_configure-loop-1.png)

## [](https://lygos.io/docs/signage/preview-loop-and-visualizations)Preview Loop and Visualizations

You can easily preview the entire complete loop or check individual visualizations before you deploy them live to your video walls.

### Preview a Single Visualization

- Simply select any visualization from your list of added items to generate a live preview showing exactly how it will render on the screen.

### Preview the Entire Loop

- Press the Play button located inside the editor to watch a preview of the full signage loop playing in its proper sequence.

Utilizing these previews helps you perfectly fine tune your content order, transitions, and timing before taking the presentation live.

![](https://lygos.io/images/docs/signage/previewLoopAndVisualizations_preview-loop-1.png)

## [](https://lygos.io/docs/signage/deploy-to-screens)Deploy to Screens

Schedules and Signage Loops generated within the Signage module can be pushed to your dashboards and video walls straight from the Signage Module or via the Display Module.

### Editor Deployment Options

**1\. Deploy**

- Choose a specific Screenspace or video wall where you want to deploy your Schedule or Signage Loop.
- Select between these two options:
  - **Add to First Available Space** - This automatically drops your Visualization into the very first empty Layout slot it finds.
  - **Replace Visualization** - This lets you swap out an existing Deployed Visualization. A list of your active deployments is provided to make selection easy.

**2\. Assign**

- You can manually Assign your Visualization to a specific Dynamic Slot, numbered 1 through 16.
- Once assigned, these slots can be:
  - Resized
  - Repositioned
  - Replaced
- You can use the Display Module Layout interface for advanced management of your Dynamic Slots.

# [](https://lygos.io/docs/presentation)PRESENTATION

The Presentation module enables users to build and present video wall wide presentations using maps, media and visualizations as well as basic texts in Lygos Environment.

**Key Features**

- You can construct slides acting as collages or layouts filled with multimedia, maps, and charts directly on your video walls.
- You can position your slides inside the grid area according to your active Screenspace Layout.
- You can quickly reorder your slides utilizing a drag and drop interface.
- You can drive your presentations using either the Control Module or the Editor.
- You can access fundamental presentation controls directly from your mobile device.
- You can push your finished presentations seamlessly to the video walls.
- You can deliver presentations utilizing the full resolution of your video wall, incorporating interactive multimedia and maps or charts fueled by real-time data.

## [](https://lygos.io/docs/presentation/create-slides)Create Slides

You can assemble collaged real-time data analytics presentations for your video walls by organizing multiple visual elements into individual slides.

**Key Features**

- **Slide Based Layouts:** Every individual slide can function as a collage or layout containing multimedia, charts, and maps.
- **Unlimited Slides:** You are free to insert an infinite number of slides into your presentation.
- **Real-time Data:** Because the visualizations stream live information, your presentation is consistently up to date.

![](https://lygos.io/images/docs/presentation/createSlides_create-slides-1.png)

You can leverage this capability to forge dynamic and insightful presentations utilizing your current visual content.

## [](https://lygos.io/docs/presentation/add-visualizations)Add Visualizations/Texts

You can elevate your video wall presentation slides by incorporating many different types of visual media.

### How to Use

- **Select a Slide:** Click the specific slide you wish to modify or build upon.
- **Choose Visualization Type:** Pick from available categories like Visualization elements, Media, Sensors, or Maps.
- **Add Elements:** Load your selected visualization element directly into the active slide.
- **Position Freely:** You can drop these visualizations into any area of your slide layout.
- **Preview Elements:** Utilize the preview function to check exactly how your visual elements will render.
- **Control:** You can manage your loaded elements by utilizing the Control button.

This workflow provides total interactivity and customization for your presentations.

![](https://lygos.io/images/docs/presentation/addVisualizations_presentation%20editor.png)

### Add Texts

As an alternative, you can insert basic text widgets to serve as headers within your presentations. You have the ability to edit and add these text widgets, placing multiple texts of any size anywhere across the grid.

![](https://lygos.io/images/docs/presentation/addVisualizations_presentation-text.png)

## [](https://lygos.io/docs/presentation/configure-presentation)Configure Presentation

You can easily customize your video wall presentations utilizing intuitive layout and slide controls.

### Features

- **Slide Ordering:** You can quickly reorganize your presentation by dragging and dropping slides inside the slide list.
- **Layout Customization:** You are free to resize and position your visualizations on every individual slide to craft the ideal layout for your video wall.
- This flexible arrangement of visual elements allows you to generate highly informative and engaging slides.

![](https://lygos.io/images/docs/presentation/configurePresentation_configure-presentation-1.png)

## [](https://lygos.io/docs/presentation/control-presentation)Control Presentation

You can seamlessly manage your presentations utilizing the built in control suite. Whether you are guiding a complex slide progression on a video wall or navigating critical analytics during a control center briefing, this tool guarantees an impactful and smooth delivery. You retain total authority over the flow and pace of your information through intuitive navigation tools that allow you to toggle visual transitions, jump between slides, and drive the presentation from external mobile interfaces or the central editor.

### Slide Navigation Options

- **First Slide:** Instantly jump back to the very beginning of the presentation.
- **Previous Slide:** Step back to the slide immediately preceding your current one.
- **Next Slide:** Move forward to the subsequent slide in your sequence.
- **Last Slide:** Skip all the way to the final slide in your presentation.
- **Toggle Transition:** You can disable or enable visual transition effects to achieve instant or smoother navigation.

![](https://lygos.io/images/docs/presentation/controlPresentation_control-presentations-1.png)

You can drive your slides utilizing external Control UIs or directly from the Editor. As you progress through the presentation on your video wall, the individual controls for the Media, Maps, and Visualizations embedded in your slides will populate on the control UI.

![](https://lygos.io/images/docs/presentation/controlPresentation_control-presentations-2.png)

As an alternative, employees and guests can dictate the presentation by scanning a QR code located on the Management Client's QR or Keys page, allowing them to drive the slides from their Mobile Devices. Additionally, they can transform their mobile device into a laser pointer to draw directly onto the slides, treating them like a whiteboard.

![](https://lygos.io/images/modules/control/04_mobile_control.png)

## [](https://lygos.io/docs/presentation/deploy-to-screens)Deploy to Screens

You can push your Presentation Visualizations to any Video Wall straight from the Presentation Editor or by utilizing the Display Module. Simply pick the size and layout that best aligns with your overall display strategy.

### Editor Deployment Options

**1\. Deploy**

- First, select the target Screenspace where you want to deploy your Presentation Visualization.
- Next, select one of these two options:
  - **Add to First Available Space:** This automatically drops your Visualization into the very first empty Layout slot it finds.
  - **Replace Visualization:** This allows you to select and overwrite an existing Deployed Visualization. The system provides a list of existing deployments to make selection easy.

**2\. Assign**

- You can manually Assign your Visualization to a specific Dynamic Slot, numbered 1 through 16.
- Once assigned, these dynamic slots can be:
  - Resized
  - Repositioned
  - Replaced
- You can utilize the Display Module Layout interface for advanced Dynamic Slot Management.

# [](https://lygos.io/docs/control)CONTROL

The Control module allows users to seamlessly manage and interact with multimedia, maps, charts, and visualizations displayed on dashboards and video walls utilizing Mobile Devices for basic controls or full Control Clients.

**Key Features**

- Control Dashboard
  - Users can select a specific screenspace to launch its associated Control Dashboard.
  - The system utilizes simplified controls accessible from the clients to easily manage complex visualizations.
  - Any modifications made within the Control Module can be completely reset for the following session.
  - You have the option to reset all changes simultaneously or individually reset controls for specific visualizations.
- Synchronization Controls
  - You can utilize temporal synchronization to animate multiple visualization series together across a shared timeline.
  - You can force multiple maps and visuals to simultaneously focus on specific regions or locations.
- Tablet Control
  - You can utilize the Lygos tablet application to scan a Control QR code, instantly logging you into that screenspace's control interface.
- Mobile Control
  - You can scan a Control QR code utilizing any standard mobile phone to access web based controls, which include:
    - **Air Mouse:** This transforms your phone into a physical pointer or pen simply by aiming it at the display screen.
    - **Presentation Control:** This provides a seamless interface to manage your presentations directly from your mobile device.

## [](https://lygos.io/docs/control/control-dashboard)Control Dashboard

Control Dashboards deliver dedicated, streamlined user interfaces built specifically for real-time interaction with the visualizations rendering on your screenspaces and layouts.

![](https://lygos.io/images/docs/control/controlDashboard_control-dashboard-1.png)

**Key Features**

- **Real-Time Control:** You can interact with and manage your visualizations live on your dashboards or video walls utilizing either the Control Client or the Management UI.
- **Select Screenspace:** The dashboard allows you to select exactly which screenspace you want to assume control over.
- **Separate Control Client:** If you launch the dashboard from the Launcher Menu, it opens a dedicated, separate control client that provides extended functionalities:
  - The ability to view your layouts.
  - Access to the Draw on Layout feature, enabling direct emphasis and annotation on the screen.

### Session Based Controls

- Any control inputs or modifications made here are temporary, remaining valid only for the duration of the active session.

### Customization

- You can utilize a simple drag and drop interface to rearrange your control elements, matching the layout to your specific screen setup and preferred workflow.

![](https://lygos.io/images/docs/control/controlDashboard_control-dashboard-2.png)

## [](https://lygos.io/docs/control/temporal-and-spatial-synchronization)Temporal and Spatial Synchronization

The Spatial and Temporal Synchronization feature guarantees that your separated data modules function together to tell a cohesive, unified narrative. This capability is critical in control room environments when operators are comparing datasets across a massive operations video wall or analyzing complex multi layered scenarios, as it allows them to lock geographic focus across several maps or link time series playback together.

By synchronizing spatial movements and animations, system administrators ensure that all connected visualizations react and move in perfect harmony, which facilitates seamless comparative analysis without requiring operators to manually adjust each individual display.

![](https://lygos.io/images/docs/control/temporalAndSpatialSynchronization_temporal-1.png)

### Temporal Synchronization

This feature synchronizes animations across varying visualizations and datasets, enabling simultaneous playback for accurate temporal comparison within control rooms.

**Supported Visualizations:**

- Map
- Visualization
- Sensors
- Watch (When utilizing Animation Mode)

**Use Case Example:** You can animate a visualization tracking temperature changes and a map tracking population growth in perfect sync over the same timeline.

### Spatial Synchronization

This feature focuses multiple distinct visualizations onto the exact same geographical area, allowing operators to execute synchronized zooming and panning across all linked modules within a control room.

**Supported Visualizations:**

- Earth
- Map
- Visualization (This is strictly limited to Spatial Data)

**Use Case Example:** When an operator zooms into a specific region on their primary map, that action simultaneously updates the focus area across all other related visualizations on the video wall.

## [](https://lygos.io/docs/control/tablet-control)Tablet Control

The dedicated Lygos Tablet App provides a seamless method for controlling the visualizations deployed on your dashboards and video walls utilizing a tablet device.

### How It Works

- You can utilize a Control QR Code to instantly connect your tablet and log into a specific Screenspace Control session.
- Alternatively, you can perform a conventional login utilizing the server IP alongside user keys or master keys (note that master keys require control level access or higher).
- Once the connection is established, you gain real-time interaction capabilities over all deployed visualizations.

**Key Features**

- Instantaneous login and connection via QR code scanning.
- Real-time interaction and manipulation of live visualizations.
- An intuitive touch based interface designed for fluid navigation and control.
- The ability to Point and Draw directly onto Video Walls, utilizing touch controls to treat the displays like whiteboards.

![](https://lygos.io/images/docs/control/tabletControl_tablet-control-1.png)

## [](https://lygos.io/docs/control/mobile-control)Mobile Control

Lygos provides fundamental control functionalities directly from any standard tablet or mobile phone, delivering interactive and flexible control over the presentations and layouts deployed to your video walls.

### Connect via QR Code

- Navigate to the 'Keys and Login' page within the software.
- Choose the specific Screenspace you wish to manage and toggle its control button.
- The system will generate a Control QR Code, which appears:
  - In the Control QR tab located at the bottom of the interface.
  - As an overlay directly on the physical target screens.
- Scan this QR code utilizing your mobile device's camera and tap the resulting link to open the web based Mobile Control interface.
- If prompted, you must allow your browser permissions for device access and motion/orientation. This step is only required if forced LAN Control is active.

### Air Mouse Control

This feature transforms your mobile phone into a virtual pointer simply by physically aiming it toward the display screen.

**Features include:**

- **Pointer & Draw:** Utilize your mobile device to digitally draw or highlight specific areas directly on the active layout.
- **Calibration:** You must calibrate the device before its first use. Ensure you remain perfectly still during the calibration process to achieve the best accuracy.
- You must grant your browser permission for Motion and Orientation access when prompted, though this is only required if forced LAN Control is active.
- You can freely customize the color and size of your digital pointer.
- Utilize the Clear function to instantly erase all drawings from the display screen.

### Presentation Controls

The Mobile Control interface grants full navigation authority over any presentations deployed to your video walls.

- If multiple presentations exist on the video wall's current layout, first select the specific presentation you wish to control.
- You can easily navigate through the slides utilizing the provided controls:
  - First
  - Previous
  - Next
  - Last

# DISCLAIMER

© 2026 KVNC R&D and Software Solutions Limited Company. All rights reserved.

This manual is prepared for Lygos Base Version 4.0.0.

## Liability and Accuracy

While we have taken every care in preparing this manual, the author and publisher accept no responsibility for errors, omissions, or any damages arising from the use of this information. The content provided is subject to change without prior notice and does not constitute a formal commitment by KVNC R&D and Software Solutions. Please refer to current documentation for latest information at: <https://lygos.io/docs> or in app documentation.

## Software Licensing

The software described herein is provided strictly under the terms of Lygos Software [EULA](https://lygos.io/eula). Users are permitted to use or copy the software only as expressly authorized by that specific agreement.

## Trademark Information

All trademarks and service marks identified in this documentation are capitalized for clarity. While KVNC R&D and Software Solutions Limited Company makes every effort to identify these marks correctly, we cannot guarantee the complete accuracy of this information. The inclusion or use of any term here does not impact the legal status or validity of any trademark or service mark.

Lygos is a trademark of KVNC R&D and Software Solutions Limited Company.
