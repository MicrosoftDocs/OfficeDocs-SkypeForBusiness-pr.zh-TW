---
title: Lync Server 2013：行動的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e1267710405cb9b6c4e64d9cf2e31fb63feddaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="554d1-102">Lync Server 2013 中行動的憑證需求</span><span class="sxs-lookup"><span data-stu-id="554d1-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="554d1-103">_**主題上次修改日期：** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="554d1-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="554d1-104">如果您部署行動性功能並支援行動用戶端的自動探索，您需要在憑證上加入特定主體替代名稱專案，以支援行動用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="554d1-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="554d1-105">您必須在下列憑證中包含主體替代名稱專案，以進行自動探索：</span><span class="sxs-lookup"><span data-stu-id="554d1-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="554d1-106">Director pool</span><span class="sxs-lookup"><span data-stu-id="554d1-106">Director pool</span></span>

  - <span data-ttu-id="554d1-107">前端集區</span><span class="sxs-lookup"><span data-stu-id="554d1-107">Front End pool</span></span>

  - <span data-ttu-id="554d1-108">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="554d1-108">Reverse proxy</span></span>

<span data-ttu-id="554d1-109">本節說明自動探索憑證所需的主體替代名稱專案。</span><span class="sxs-lookup"><span data-stu-id="554d1-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="554d1-110">使用內部憑證授權單位重新發出憑證通常是很簡單的程序，但是新增多個主體替代名稱項目至反向 Proxy 所使用的公用憑證會很昂貴。</span><span class="sxs-lookup"><span data-stu-id="554d1-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="554d1-111">如果您有多個 SIP 網域，增加主體別名的加入是非常昂貴的，您可以設定反向 proxy 使用 HTTP 來進行初始自動探索服務要求，而不是使用 HTTPS (預設設定) 。</span><span class="sxs-lookup"><span data-stu-id="554d1-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="554d1-112">如需詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中行動的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="554d1-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="554d1-113">Director 集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="554d1-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="554d1-114">描述</span><span class="sxs-lookup"><span data-stu-id="554d1-114">Description</span></span></th>
<th><span data-ttu-id="554d1-115">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="554d1-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="554d1-116">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="554d1-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="554d1-117">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="554d1-118">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="554d1-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="554d1-119">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="554d1-120">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="554d1-121">前端集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="554d1-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="554d1-122">描述</span><span class="sxs-lookup"><span data-stu-id="554d1-122">Description</span></span></th>
<th><span data-ttu-id="554d1-123">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="554d1-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="554d1-124">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="554d1-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="554d1-125">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="554d1-126">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="554d1-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="554d1-127">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="554d1-128">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="554d1-129">反向 Proxy (公用 CA) 憑證需求</span><span class="sxs-lookup"><span data-stu-id="554d1-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="554d1-130">描述</span><span class="sxs-lookup"><span data-stu-id="554d1-130">Description</span></span></th>
<th><span data-ttu-id="554d1-131">主體別名項目</span><span class="sxs-lookup"><span data-stu-id="554d1-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="554d1-132">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="554d1-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="554d1-133">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="554d1-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="554d1-134">您將此 SAN 指派給反向 proxy 上的 SSL 接聽程式所指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="554d1-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="554d1-135">如果您已部署選用的 Director) ，您的反向 proxy 攔截器將會有您的外部 Web 服務 URL 的主體替代名稱 (s)  (例如 SAN=lyncwebextpool01.contoso.com 及 dirwebexternal.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="554d1-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

