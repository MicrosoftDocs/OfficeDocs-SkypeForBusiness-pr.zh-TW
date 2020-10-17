---
title: Lync Server 2013：驗證位址
description: Lync Server 2013：驗證位址。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547269"
---
# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="45bf7-103">在 Lync Server 2013 中驗證位址</span><span class="sxs-lookup"><span data-stu-id="45bf7-103">Validate addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45bf7-104">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="45bf7-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="45bf7-105">在發佈位置資料庫之前，您必須對照主要街道通訊指南 (MSAG) （由 SIP 主幹或公用交換電話網路 (PSTN) E9-1-1 服務提供者所維護）驗證新的位置。</span><span class="sxs-lookup"><span data-stu-id="45bf7-105">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="45bf7-106">如需 SIP 主幹 E9-1-1 服務提供者的詳細資訊，請參閱 [選擇 E9-1-1 服務提供者以進行 Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="45bf7-106">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="45bf7-107">如需驗證位址的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="45bf7-107">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="45bf7-108">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="45bf7-108">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="45bf7-109">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="45bf7-109">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="45bf7-110">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="45bf7-110">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="45bf7-111">**CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="45bf7-111">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="45bf7-112">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="45bf7-112">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="45bf7-113">驗證位於位置資料庫中的位址</span><span class="sxs-lookup"><span data-stu-id="45bf7-113">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="45bf7-114">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="45bf7-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45bf7-115">執行下列 Cmdlet 以設定緊急服務提供者連線。</span><span class="sxs-lookup"><span data-stu-id="45bf7-115">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="45bf7-116">執行下列 Cmdlet 來驗證位置資料庫中的位址。</span><span class="sxs-lookup"><span data-stu-id="45bf7-116">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="45bf7-117">您也可以使用 **Test-CsLisCivicAddress** Cmdlet 來驗證個別的位址。</span><span class="sxs-lookup"><span data-stu-id="45bf7-117">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

