---
title: Lync Server 2013：行動的憑證需求
description: Lync Server 2013：行動的憑證需求。
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
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575199"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="5ee7c-103">Lync Server 2013 中行動的憑證需求</span><span class="sxs-lookup"><span data-stu-id="5ee7c-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ee7c-104">_**主題上次修改日期：** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="5ee7c-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="5ee7c-105">如果您部署行動性功能並支援行動用戶端的自動探索，您需要在憑證上加入特定主體替代名稱專案，以支援行動用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="5ee7c-106">您必須在下列憑證中包含主體替代名稱專案，以進行自動探索：</span><span class="sxs-lookup"><span data-stu-id="5ee7c-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="5ee7c-107">Director pool</span><span class="sxs-lookup"><span data-stu-id="5ee7c-107">Director pool</span></span>

  - <span data-ttu-id="5ee7c-108">前端集區</span><span class="sxs-lookup"><span data-stu-id="5ee7c-108">Front End pool</span></span>

  - <span data-ttu-id="5ee7c-109">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="5ee7c-109">Reverse proxy</span></span>

<span data-ttu-id="5ee7c-110">本節說明自動探索憑證所需的主體替代名稱專案。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ee7c-111">使用內部憑證授權單位重新發出憑證通常是很簡單的程序，但是新增多個主體替代名稱項目至反向 Proxy 所使用的公用憑證會很昂貴。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="5ee7c-112">如果您有多個 SIP 網域，增加主體別名的加入是非常昂貴的，您可以設定反向 proxy 使用 HTTP 來進行初始自動探索服務要求，而不是使用 HTTPS (預設設定) 。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="5ee7c-113">如需詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中行動的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="5ee7c-114">Director 集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="5ee7c-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee7c-115">描述</span><span class="sxs-lookup"><span data-stu-id="5ee7c-115">Description</span></span></th>
<th><span data-ttu-id="5ee7c-116">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="5ee7c-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee7c-117">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="5ee7c-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ee7c-118">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee7c-119">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="5ee7c-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ee7c-120">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ee7c-121">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="5ee7c-122">前端集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="5ee7c-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee7c-123">描述</span><span class="sxs-lookup"><span data-stu-id="5ee7c-123">Description</span></span></th>
<th><span data-ttu-id="5ee7c-124">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="5ee7c-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee7c-125">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="5ee7c-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ee7c-126">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee7c-127">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="5ee7c-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ee7c-128">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ee7c-129">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="5ee7c-130">反向 Proxy (公用 CA) 憑證需求</span><span class="sxs-lookup"><span data-stu-id="5ee7c-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee7c-131">描述</span><span class="sxs-lookup"><span data-stu-id="5ee7c-131">Description</span></span></th>
<th><span data-ttu-id="5ee7c-132">主體別名項目</span><span class="sxs-lookup"><span data-stu-id="5ee7c-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee7c-133">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="5ee7c-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ee7c-134">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee7c-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ee7c-135">您將此 SAN 指派給反向 proxy 上的 SSL 接聽程式所指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5ee7c-136">如果您已部署選用的 Director) ，您的反向 proxy 攔截器將會有您的外部 Web 服務 URL 的主體替代名稱 (s)  (例如 SAN=lyncwebextpool01.contoso.com 及 dirwebexternal.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5ee7c-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

