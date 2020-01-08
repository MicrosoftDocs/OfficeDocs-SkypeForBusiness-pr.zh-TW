---
title: Lync Server 2013：設定反向 Proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="4bdeb-102">在 Lync Server 2013 中設定反向 Proxy 的憑證</span><span class="sxs-lookup"><span data-stu-id="4bdeb-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bdeb-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4bdeb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4bdeb-104">每個反向 proxy 伺服器都需要有可供偵聽服務使用的 web 伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="4bdeb-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="4bdeb-105">Web 服務器憑證必須由公用憑證授權單位（CA）頒發。</span><span class="sxs-lookup"><span data-stu-id="4bdeb-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="4bdeb-106">如需有關此和其他證書需求的詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4bdeb-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="4bdeb-107">針對反向 proxy 設定 Web 服務憑證</span><span class="sxs-lookup"><span data-stu-id="4bdeb-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="4bdeb-108">您應該已設定您的反向 proxy，包括設定 Web 服務憑證。</span><span class="sxs-lookup"><span data-stu-id="4bdeb-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="4bdeb-109">如果您在開始部署邊緣伺服器之前沒有這麼做，請使用[設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的程式來建立要求並安裝 web 服務憑證，然後建立每個 web 發佈規則，並將其設定為使用憑證。</span><span class="sxs-lookup"><span data-stu-id="4bdeb-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

