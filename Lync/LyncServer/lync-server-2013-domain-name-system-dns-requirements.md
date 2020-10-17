---
title: Lync Server 2013：網域名稱系統 (DNS) 需求
description: Lync Server 2013：網域名稱系統 (DNS) 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84868d4929cc410cddbb6c9ad2019a12841e80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553199"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="4866a-103">Lync Server 2013 (DNS) 需求的網域名稱系統</span><span class="sxs-lookup"><span data-stu-id="4866a-103">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4866a-104">_**主題上次修改日期：** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="4866a-104">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="4866a-105">若要部署 Lync Server，您必須建立網域名稱系統 (DNS) 記錄，以啟用用戶端和伺服器的探索，並選擇性地支援自動用戶端登入（如果您的組織想要支援它）。</span><span class="sxs-lookup"><span data-stu-id="4866a-105">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="4866a-106">Lync Server 使用 DNS 的方式如下：</span><span class="sxs-lookup"><span data-stu-id="4866a-106">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="4866a-107">探索內部伺服器或集區以進行伺服器對伺服器的通訊。</span><span class="sxs-lookup"><span data-stu-id="4866a-107">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="4866a-108">允許用戶端探索用於各種 SIP 交易的前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="4866a-108">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="4866a-109">若要允許整合通訊 (未登入的 UC) 裝置，探索執行裝置更新 Web 服務的前端集區或 Standard Edition server、取得更新及傳送記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4866a-109">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="4866a-110">若要允許外部伺服器及用戶端連線至 Edge Server 或 HTTP 反向 proxy 以進行立即訊息 (IM) 或會議。</span><span class="sxs-lookup"><span data-stu-id="4866a-110">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="4866a-111">以允許外部 UC 裝置透過 Edge Server 或 HTTP 反向 proxy 連線至裝置更新 Web 服務，並取得更新。</span><span class="sxs-lookup"><span data-stu-id="4866a-111">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="4866a-112">讓行動用戶端能夠自動探索 Web 服務資源，而不需使用者手動在裝置設定中輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="4866a-112">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4866a-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4866a-113">In This Section</span></span>

  - [<span data-ttu-id="4866a-114">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-114">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="4866a-115">Lync Server 2013 中前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-115">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="4866a-116">Lync Server 2013 的 Standard Edition server 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-116">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="4866a-117">Lync Server 2013 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-117">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="4866a-118">Lync Server 2013 中自動用戶端登入的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-118">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="4866a-119">使用 Lync Server 2013 行動的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4866a-119">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="4866a-120">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="4866a-120">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

