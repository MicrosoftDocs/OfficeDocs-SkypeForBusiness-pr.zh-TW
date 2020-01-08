---
title: Lync Server 2013：網功能變數名稱稱系統（DNS）需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="eed7a-102">Lync Server 2013 的網域名稱系統（DNS）需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed7a-103">_**主題上次修改日期：** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="eed7a-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="eed7a-104">若要部署 Lync Server，您必須建立可讓用戶端與伺服器探索的網域名稱系統（DNS）記錄，而且（如果您的組織想要支援，也可以選擇）支援自動用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="eed7a-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="eed7a-105">Lync Server 使用 DNS 的方式如下：</span><span class="sxs-lookup"><span data-stu-id="eed7a-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="eed7a-106">探索內部伺服器或池以進行伺服器間的通訊。</span><span class="sxs-lookup"><span data-stu-id="eed7a-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="eed7a-107">允許用戶端探索用於各種 SIP 事務的前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="eed7a-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="eed7a-108">若要允許未登入的整合通訊（UC）裝置探索執行裝置更新 Web 服務的前端池或標準版伺服器，請取得更新並傳送記錄。</span><span class="sxs-lookup"><span data-stu-id="eed7a-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="eed7a-109">允許外部伺服器和用戶端連線至 Edge 伺服器或 HTTP 反向 proxy，以取得立即訊息（IM）或會議。</span><span class="sxs-lookup"><span data-stu-id="eed7a-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="eed7a-110">若要允許外部 UC 裝置透過邊緣伺服器或 HTTP 反向 proxy 連線到裝置更新 Web 服務，並取得更新。</span><span class="sxs-lookup"><span data-stu-id="eed7a-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="eed7a-111">若要允許行動用戶端自動探索 Web 服務資源，而不需要使用者在 [裝置設定] 中手動輸入 Url。</span><span class="sxs-lookup"><span data-stu-id="eed7a-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eed7a-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="eed7a-112">In This Section</span></span>

  - [<span data-ttu-id="eed7a-113">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="eed7a-114">Lync Server 2013 中前端池的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="eed7a-115">Lync Server 2013 中標準版伺服器的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="eed7a-116">Lync Server 2013 中簡單 URL 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="eed7a-117">在 Lync Server 2013 中自動用戶端登入的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="eed7a-118">使用 Lync Server 2013 行動的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="eed7a-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="eed7a-119">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="eed7a-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

