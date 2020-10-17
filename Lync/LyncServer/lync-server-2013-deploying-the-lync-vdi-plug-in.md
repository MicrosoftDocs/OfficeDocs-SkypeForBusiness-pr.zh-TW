---
title: Lync Server 2013：部署 Lync VDI 外掛程式
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
ms.openlocfilehash: 160ca4459a73697e1a4dc82c9fd4b680e16f7beb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522860"
---
# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="544b7-102">在 Lync Server 2013 中部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="544b7-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="544b7-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="544b7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="544b7-104">Lync 2013 用戶端支援虛擬桌面基礎結構中的音訊和影片 (VDI) 環境。</span><span class="sxs-lookup"><span data-stu-id="544b7-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="544b7-105">使用者可以將音訊和視訊裝置 (例如，耳機或相機) 連線至本機電腦 (例如，精簡型用戶端或重新設定功能的電腦)。</span><span class="sxs-lookup"><span data-stu-id="544b7-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="544b7-106">使用者可以連線至虛擬機器，登入虛擬機器上執行的 Lync 2013 用戶端，並參與即時音訊和視頻通訊，如同用戶端在本機執行。</span><span class="sxs-lookup"><span data-stu-id="544b7-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="544b7-107">Lync VDI 外掛程式是安裝在本機電腦上的獨立應用程式，可讓本機音訊和影片裝置使用於虛擬機器上執行的 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="544b7-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="544b7-108">外掛程式不需要在本機電腦上安裝 Lync。</span><span class="sxs-lookup"><span data-stu-id="544b7-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="544b7-109">在使用者登入虛擬機器上執行的 Lync 2013 用戶端後，Lync 會提示使用者重新輸入其認證，以與本機電腦上執行的 Lync VDI 外掛程式建立連線。</span><span class="sxs-lookup"><span data-stu-id="544b7-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="544b7-110">在建立此連線之後，使用者就可以開始和接收音訊和影片通話。</span><span class="sxs-lookup"><span data-stu-id="544b7-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="544b7-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="544b7-111">In This Section</span></span>

  - [<span data-ttu-id="544b7-112">Lync Server 2013 中的 lync VDI 外掛程式必要條件</span><span class="sxs-lookup"><span data-stu-id="544b7-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="544b7-113">為 VDI 準備 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="544b7-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="544b7-114">在虛擬機器上登入和使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="544b7-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="544b7-115">Lync Server 2013 中的 Lync VDI 外掛程式疑難排解</span><span class="sxs-lookup"><span data-stu-id="544b7-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="544b7-116">Lync Server 2013 中支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="544b7-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

