---
title: Lync Server 2013： 網域名稱系統 (DNS) 需求
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
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="abd9e-102">Lync Server 2013 的網域名稱系統 (DNS) 需求</span><span class="sxs-lookup"><span data-stu-id="abd9e-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd9e-103">_**主題上次修改日期：** 2012年-06-18_</span><span class="sxs-lookup"><span data-stu-id="abd9e-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="abd9e-104">若要部署 Lync Server，您必須建立網域名稱系統 (DNS) 記錄，可讓您的用戶端和伺服器探索，以及 （選用） 如果您的組織想要支援的話支援的用戶端自動登入。</span><span class="sxs-lookup"><span data-stu-id="abd9e-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="abd9e-105">Lync Server 以下列方式使用 DNS:</span><span class="sxs-lookup"><span data-stu-id="abd9e-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="abd9e-106">探索內部伺服器或集區以進行伺服器對伺服器的通訊。</span><span class="sxs-lookup"><span data-stu-id="abd9e-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="abd9e-107">若要允許用戶端探索用於各種 SIP 交易的 Standard Edition server 的前端集區。</span><span class="sxs-lookup"><span data-stu-id="abd9e-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="abd9e-108">若要允許未登入可探索的前端集區或 Standard Edition 伺服器執行裝置更新 Web 服務的整合的通訊 (UC) 裝置，取得更新以及傳送記錄檔。</span><span class="sxs-lookup"><span data-stu-id="abd9e-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="abd9e-109">允許外部伺服器與用戶端連線至 Edge Server 或 HTTP 反向 proxy 進行立即訊息 (IM) 或會議。</span><span class="sxs-lookup"><span data-stu-id="abd9e-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="abd9e-110">若要允許外部 UC 裝置能夠連線至裝置更新 Web 服務，透過 Edge Server 或 HTTP 反向 proxy，並取得更新。</span><span class="sxs-lookup"><span data-stu-id="abd9e-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="abd9e-111">讓行動用戶端能夠自動探索 Web 服務資源，而不需使用者手動在裝置設定中輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="abd9e-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abd9e-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="abd9e-112">In This Section</span></span>

  - [<span data-ttu-id="abd9e-113">決定針對 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="abd9e-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="abd9e-114">Lync Server 2013 中的前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="abd9e-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - <span data-ttu-id="abd9e-115">[在 [Lync Server 2013 Standard Edition server 的 DNS 需求](lync-server-2013-dns-requirements-for-standard-edition-servers.md)</span><span class="sxs-lookup"><span data-stu-id="abd9e-115">[DNS requirements for Standard Edition servers in Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)</span></span>

  - [<span data-ttu-id="abd9e-116">Lync Server 2013 中的簡單 Url 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="abd9e-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="abd9e-117">DNS 需求的用戶端自動登入 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="abd9e-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="abd9e-118">搭配 Lync Server 2013 的行動的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="abd9e-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="abd9e-119">DNS 負載平衡 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="abd9e-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

