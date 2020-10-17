---
title: Lync Server 2013：設定位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9495bc0c52e8e9af4af0daa3d29304d5b25d4b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520260"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2253d-102">在 Lync Server 2013 中設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="2253d-102">Configure the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2253d-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2253d-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2253d-104">若要讓用戶端自動偵測網路內部的位置，您必須先設定位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="2253d-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="2253d-105">如果您未設定位置資料庫，且位置原則中 **所需的位置** 已設定為 **[是] 或 [** **免責聲明**]，則系統會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="2253d-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="2253d-106">若要設定位置資料庫，您需要執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2253d-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="2253d-107">以網元對應至位置，填入資料庫。</span><span class="sxs-lookup"><span data-stu-id="2253d-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="2253d-108">如果您使用緊急位置識別號碼 (ELIN) 閘道，您必須在欄位中包含 ELIN \<CompanyName\> 。</span><span class="sxs-lookup"><span data-stu-id="2253d-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="2253d-109">對照主要街道通訊指南 (MSAG) 來驗證 E9-1-1 服務提供者所維護的位址。</span><span class="sxs-lookup"><span data-stu-id="2253d-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="2253d-110">發佈更新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2253d-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2253d-111">或者，您也可以定義可用於放置位置資料庫的次要位置來源資料庫。</span><span class="sxs-lookup"><span data-stu-id="2253d-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="2253d-112">如需詳細資訊，請參閱 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a 次要位置資訊服務中的 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="2253d-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2253d-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2253d-113">In This Section</span></span>

  - [<span data-ttu-id="2253d-114">在 Lync Server 2013 中填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="2253d-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="2253d-115">在 Lync Server 2013 中驗證位址</span><span class="sxs-lookup"><span data-stu-id="2253d-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="2253d-116">從 Lync Server 2013 發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="2253d-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

