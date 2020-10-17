---
title: Lync Server 2013：設定反向 proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509870"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="0d3b6-102">在 Lync Server 2013 中設定反向 proxy 的憑證</span><span class="sxs-lookup"><span data-stu-id="0d3b6-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d3b6-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0d3b6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0d3b6-104">每個反向 proxy 伺服器都需要一個網頁伺服器憑證，以供接聽服務使用。</span><span class="sxs-lookup"><span data-stu-id="0d3b6-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="0d3b6-105">網頁伺服器憑證必須由公用憑證授權單位單位 (CA) 所發行。</span><span class="sxs-lookup"><span data-stu-id="0d3b6-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="0d3b6-106">如需此和其他憑證需求的詳細資訊，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0d3b6-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="0d3b6-107">設定反向 proxy 的 Web 服務憑證</span><span class="sxs-lookup"><span data-stu-id="0d3b6-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="0d3b6-108">您應該已經設定反向 proxy （包括設定 Web 服務憑證）。</span><span class="sxs-lookup"><span data-stu-id="0d3b6-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="0d3b6-109">如果您在開始部署 Edge Server 之前未執行此動作，請使用 [設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md) 中的程式來建立要求並安裝 web 服務憑證，然後建立每個 web 發佈規則，並將其設定為使用憑證。</span><span class="sxs-lookup"><span data-stu-id="0d3b6-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

