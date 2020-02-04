---
title: Lync Server 2013：驗證位址
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="e691e-102">驗證 Lync Server 2013 中的位址</span><span class="sxs-lookup"><span data-stu-id="e691e-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e691e-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e691e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e691e-104">在發佈位置資料庫之前，您必須針對由 SIP 主幹或公用交換電話網絡（PSTN） E9-1-1 服務提供者維護的主要街道位址指南（MSAG）驗證新的位置。</span><span class="sxs-lookup"><span data-stu-id="e691e-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="e691e-105">如需 SIP 幹線 E9-1-1 服務提供者的詳細資料，請參閱[選擇 Lync Server 2013 的 E9 服務提供者](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e691e-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="e691e-106">如需驗證位址的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="e691e-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e691e-107">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e691e-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e691e-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e691e-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e691e-109">**移除-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e691e-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e691e-110">**CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="e691e-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="e691e-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="e691e-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="e691e-112">驗證位於位置資料庫中的位址</span><span class="sxs-lookup"><span data-stu-id="e691e-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="e691e-113">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e691e-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e691e-114">執行下列 Cmdlet 來設定緊急服務提供者連線。</span><span class="sxs-lookup"><span data-stu-id="e691e-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="e691e-115">執行下列 Cmdlet 以驗證位置資料庫中的位址。</span><span class="sxs-lookup"><span data-stu-id="e691e-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="e691e-116">您也可以使用**Test CsLisCivicAddress** Cmdlet 來驗證個別的位址。</span><span class="sxs-lookup"><span data-stu-id="e691e-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

