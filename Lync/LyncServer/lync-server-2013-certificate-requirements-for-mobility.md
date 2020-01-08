---
title: Lync Server 2013：行動憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e6e77-102">Lync Server 2013 中的行動憑證需求</span><span class="sxs-lookup"><span data-stu-id="e6e77-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6e77-103">_**主題上次修改日期：** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="e6e77-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="e6e77-104">如果您部署行動裝置功能，且支援行動用戶端的自動探索，您必須在憑證上包含特定的消費者替換名稱專案，以支援行動用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="e6e77-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="e6e77-105">您必須在下列憑證上包含消費者備用名稱專案，才能自動探索：</span><span class="sxs-lookup"><span data-stu-id="e6e77-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="e6e77-106">主管池</span><span class="sxs-lookup"><span data-stu-id="e6e77-106">Director pool</span></span>

  - <span data-ttu-id="e6e77-107">前端集區</span><span class="sxs-lookup"><span data-stu-id="e6e77-107">Front End pool</span></span>

  - <span data-ttu-id="e6e77-108">反向 proxy</span><span class="sxs-lookup"><span data-stu-id="e6e77-108">Reverse proxy</span></span>

<span data-ttu-id="e6e77-109">本節說明您在自動探索的憑證上所需的主題替換名稱專案。</span><span class="sxs-lookup"><span data-stu-id="e6e77-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6e77-110">使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但新增多個 subject 替換名稱專案到反向 proxy 使用的公用憑證可能會很昂貴。</span><span class="sxs-lookup"><span data-stu-id="e6e77-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="e6e77-111">如果您有多個 SIP 網域，增加消費者備用名稱的費用非常昂貴，您可以將反向 proxy 設定為使用 HTTP 取得初始自動探索服務要求，而不是使用 HTTPS （預設設定）。</span><span class="sxs-lookup"><span data-stu-id="e6e77-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="e6e77-112">如需詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中行動的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="e6e77-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="e6e77-113">控制器池證書需求</span><span class="sxs-lookup"><span data-stu-id="e6e77-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6e77-114">描述</span><span class="sxs-lookup"><span data-stu-id="e6e77-114">Description</span></span></th>
<th><span data-ttu-id="e6e77-115">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="e6e77-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6e77-116">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="e6e77-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e6e77-117">SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6e77-118">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="e6e77-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e6e77-119">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e6e77-120">或者，您也可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="e6e77-121">前端池憑證需求</span><span class="sxs-lookup"><span data-stu-id="e6e77-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6e77-122">描述</span><span class="sxs-lookup"><span data-stu-id="e6e77-122">Description</span></span></th>
<th><span data-ttu-id="e6e77-123">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="e6e77-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6e77-124">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="e6e77-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e6e77-125">SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6e77-126">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="e6e77-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e6e77-127">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e6e77-128">或者，您也可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="e6e77-129">反向 Proxy （公用 CA）憑證需求</span><span class="sxs-lookup"><span data-stu-id="e6e77-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6e77-130">描述</span><span class="sxs-lookup"><span data-stu-id="e6e77-130">Description</span></span></th>
<th><span data-ttu-id="e6e77-131">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="e6e77-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6e77-132">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="e6e77-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e6e77-133">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e6e77-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e6e77-134">您可以將這個 SAN 指派給在反向 proxy 上指派給 SSL 監聽程式的憑證。</span><span class="sxs-lookup"><span data-stu-id="e6e77-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e6e77-135">您的反向 proxy 偵聽程式將會針對您的外部 Web 服務 URL （例如 SAN = lyncwebextpool01 .com）及 dirwebexternal.contoso.com （如果您已部署選用的控制器），提供消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e6e77-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

