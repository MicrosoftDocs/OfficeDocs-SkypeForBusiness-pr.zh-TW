---
title: Lync Server 2013： 部署 Lync VDI 外掛程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 578825b8dcf7262475fa14cd2e116859f2828878
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="8658c-102">部署 Lync VDI 外掛程式 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="8658c-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8658c-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="8658c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8658c-104">Lync 2013 用戶端支援音訊和視訊虛擬桌面基礎結構 (VDI) 環境中。</span><span class="sxs-lookup"><span data-stu-id="8658c-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="8658c-105">使用者可以將音訊和視訊裝置 (例如，耳機或相機) 連線至本機電腦 (例如，精簡型用戶端或重新設定功能的電腦)。</span><span class="sxs-lookup"><span data-stu-id="8658c-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="8658c-106">使用者可以連線至虛擬機器、 登入是虛擬機器執行，Lync 2013 用戶端和一樣用戶端在本機上執行，參與即時音訊及視訊通訊。</span><span class="sxs-lookup"><span data-stu-id="8658c-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="8658c-107">Lync VDI Plug-in 是獨立的應用程式，會在本機電腦上安裝，並使用本機音訊和視訊裝置允許與 Lync 2013 用戶端在虛擬機器上執行。</span><span class="sxs-lookup"><span data-stu-id="8658c-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="8658c-108">外掛程式不需要在本機電腦上安裝 Lync。</span><span class="sxs-lookup"><span data-stu-id="8658c-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="8658c-109">使用者登入 Lync 2013 用戶端在虛擬機器上執行後，Lync 會提示使用者重新輸入他/她的認證，以建立與本機電腦執行 Lync VDI 外掛程式的連線。</span><span class="sxs-lookup"><span data-stu-id="8658c-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="8658c-110">建立此連線之後，使用者已準備好撥打及接聽音訊和視訊通話。</span><span class="sxs-lookup"><span data-stu-id="8658c-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8658c-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="8658c-111">In This Section</span></span>

  - [<span data-ttu-id="8658c-112">Lync Server 2013 中的 Lync VDI 外掛程式先決條件</span><span class="sxs-lookup"><span data-stu-id="8658c-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="8658c-113">針對 VDI 準備 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="8658c-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="8658c-114">登入和虛擬機器上使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8658c-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="8658c-115">疑難排解 Lync VDI 外掛程式 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="8658c-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="8658c-116">支援的虛擬化技術和 Lync Server 2013 中的已知的限制</span><span class="sxs-lookup"><span data-stu-id="8658c-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

