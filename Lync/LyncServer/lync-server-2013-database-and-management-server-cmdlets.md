---
title: Lync Server 2013： 資料庫和管理伺服器 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database and Management Server cmdlets
ms:assetid: b323bd59-8f71-4f03-af94-f3afb8620f4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415671(v=OCS.15)
ms:contentKeyID: 48185174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25bf5b464b8bda91d2374811d3c727154d1ceccc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-and-management-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="47683-102">Lync Server 2013 的資料庫和管理伺服器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="47683-102">Database and Management Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47683-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="47683-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="47683-104">資料庫和管理伺服器 cmdlet 可用來管理您的 Microsoft Lync Server 2013 後端資料庫與您的前端管理服務。</span><span class="sxs-lookup"><span data-stu-id="47683-104">The database and Management Server cmdlets are used to manage both your Microsoft Lync Server 2013 back-end databases and your front-end management services.</span></span> <span data-ttu-id="47683-105">您可以使用這些 cmdlet 來安裝或解除安裝任何使用 Lync Server 2013 中，除了設定中央管理存放區的 Active Directory 服務控制點的資料庫。</span><span class="sxs-lookup"><span data-stu-id="47683-105">You can use these cmdlets to install or uninstall any of the databases used by Lync Server 2013, in addition to configuring the Active Directory service control point for the Central Management store.</span></span>

<div>

## <a name="database-and-management-server-cmdlets"></a><span data-ttu-id="47683-106">資料庫和管理伺服器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="47683-106">Database and Management Server Cmdlets</span></span>

<span data-ttu-id="47683-107">以下是 cmdlet 的與管理資料庫和管理伺服器直接相關清單：</span><span class="sxs-lookup"><span data-stu-id="47683-107">The following is a list of cmdlets that relate directly to managing databases and the Management Server:</span></span>

<span data-ttu-id="47683-108">**資料庫和管理伺服器**</span><span class="sxs-lookup"><span data-stu-id="47683-108">**Databases and Management Server**</span></span>

  - <span></span>  
    <span data-ttu-id="47683-109">[Get-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-110">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-111">[Set-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47683-112">[Install-csdatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-112">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-113">[Test-csdatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-113">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-114">[Uninstall-csdatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="47683-115">[叫用 CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="47683-116">[Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="47683-117">[Install-csmirrordatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="47683-118">[解除安裝 CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47683-119">[Get-csuserdatabasestate](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-120">[設定 CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47683-121">[更新 CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-121">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47683-122">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-122">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47683-123">[Set-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-123">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="47683-124">[叫用 CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47683-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47683-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="47683-125">See Also</span></span>


[<span data-ttu-id="47683-126">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="47683-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

