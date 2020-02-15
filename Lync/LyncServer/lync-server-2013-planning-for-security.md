---
title: Lync Server 2013： 規劃安全性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bcc5c5cb36717084f9ec5715feb30b11ced5a3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="2c2f7-102">Lync Server 2013 中的安全性規劃</span><span class="sxs-lookup"><span data-stu-id="2c2f7-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c2f7-103">_**主題上次修改日期：** 2016年-06-22_</span><span class="sxs-lookup"><span data-stu-id="2c2f7-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="2c2f7-104">使用此安全性] 區段中，評定和管理您的部署 Lync Server 2013 的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="2c2f7-105">即使您的 Lync Server 2013 部署是太大，您可能必須在您的網路中有自己的安全性文件的元件。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="2c2f7-106">因此，也不太可能本節涵蓋所有元件和區域的改變您的部署安全性的各個層面。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="2c2f7-107">做為起點這個區段可用來處理 Lync Server 2013 部署的安全性。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="2c2f7-108">它可以用來評估及管理最常見的安全性風險中提供一般指導方針和最佳作法。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="2c2f7-109">其他的產品與安全性資源會列出每個主題結尾處。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c2f7-110">安全性是一個持續不斷變化的主題。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="2c2f7-111">為新的威脅與解決方案發生，以最新的材料應該取代過期文件、 解決方案、 方法及程序。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c2f7-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2c2f7-112">In This Section</span></span>

  - [<span data-ttu-id="2c2f7-113">Lync Server 2013 中的關鍵安全性功能</span><span class="sxs-lookup"><span data-stu-id="2c2f7-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="2c2f7-114">新式天運算的常見安全性威脅</span><span class="sxs-lookup"><span data-stu-id="2c2f7-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="2c2f7-115">防毒掃描排除的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c2f7-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="2c2f7-116">Lync Server 2013 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="2c2f7-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="2c2f7-117">處理 Lync Server 2013 的核心基礎結構的威脅</span><span class="sxs-lookup"><span data-stu-id="2c2f7-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="2c2f7-118">部署 SQL Server 使用非標準連接埠和 Lync Server 2013 中的別名</span><span class="sxs-lookup"><span data-stu-id="2c2f7-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

