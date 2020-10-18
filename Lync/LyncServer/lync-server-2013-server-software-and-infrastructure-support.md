---
title: Lync Server 2013：伺服器軟體和基礎結構支援
description: Lync Server 2013：伺服器軟體和基礎結構支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server software and infrastructure support
ms:assetid: 4ee5fe38-0191-4710-9aa2-df8895e8c51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398319(v=OCS.15)
ms:contentKeyID: 48184127
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a141f40b3ebee84fade10dfbfb8c8b96ef67434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580149"
---
# <a name="server-software-and-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="fd77b-103">Lync Server 2013 中的伺服器軟體和基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-103">Server software and infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd77b-104">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="fd77b-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="fd77b-105">伺服器元件的軟體支援（包括所有的 Lync Server 2013 伺服器角色及儲存體）包括支援的作業系統、資料庫軟體、基礎結構軟體，以及支援特定功能所需的其他軟體。</span><span class="sxs-lookup"><span data-stu-id="fd77b-105">Software support for server components, including all Lync Server 2013 server roles and storage, includes supported operating systems, database software, infrastructure software, and other software required to support specific functionality.</span></span> <span data-ttu-id="fd77b-106">也包括伺服器元件的虛擬化。</span><span class="sxs-lookup"><span data-stu-id="fd77b-106">It also includes virtualization of server components.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd77b-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="fd77b-107">In This Section</span></span>

  - [<span data-ttu-id="fd77b-108">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-108">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="fd77b-109">Lync Server 2013 中的資料庫軟體支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-109">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="fd77b-110">Lync Server 2013 中的 Exchange Server 和 SharePoint 整合支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-110">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)

  - [<span data-ttu-id="fd77b-111">Lync Server 2013 中的憑證基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-111">Certificate infrastructure support in Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-support.md)

  - [<span data-ttu-id="fd77b-112">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-112">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)

  - [<span data-ttu-id="fd77b-113">Lync Server 2013 中的 DNS 基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-113">DNS infrastructure support in Lync Server 2013</span></span>](lync-server-2013-dns-infrastructure-support.md)

  - [<span data-ttu-id="fd77b-114">Lync Server 2013 中的 IIS 支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-114">IIS support in Lync Server 2013</span></span>](lync-server-2013-iis-support.md)

  - [<span data-ttu-id="fd77b-115">Lync Server 2013 中的 IP 和網路通訊協定支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-115">IP and networking protocol support in Lync Server 2013</span></span>](lync-server-2013-ip-and-networking-protocol-support.md)

  - [<span data-ttu-id="fd77b-116">Lync Server 2013 中的公用立即訊息支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-116">Public instant messaging support in Lync Server 2013</span></span>](lync-server-2013-public-instant-messaging-support.md)

  - [<span data-ttu-id="fd77b-117">Lync Server 2013 控制台的瀏覽器支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-117">Browser support for Lync Server 2013 Control Panel</span></span>](lync-server-2013-browser-support-for-lync-server-control-panel.md)

  - [<span data-ttu-id="fd77b-118">Lync Server 2013 中的語音支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-118">Voice support in Lync Server 2013</span></span>](lync-server-2013-voice-support.md)

  - [<span data-ttu-id="fd77b-119">Lync Server 2013 中的虛擬化支援</span><span class="sxs-lookup"><span data-stu-id="fd77b-119">Virtualization support in Lync Server 2013</span></span>](lync-server-2013-virtualization-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

