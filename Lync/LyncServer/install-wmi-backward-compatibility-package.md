---
title: 安裝 WMI 回溯相容性套件
description: 安裝 WMI 回溯相容性套件。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9062e209981fd180b8772801960bd94d2256513a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568989"
---
# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="64c97-103">安裝 WMI 回溯相容性套件</span><span class="sxs-lookup"><span data-stu-id="64c97-103">Install WMI Backward Compatibility package</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64c97-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="64c97-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="64c97-105">若您未安裝 WMI 回溯相容性套件，而嘗試啟動 [拓撲產生器合併精靈]，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="64c97-105">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="64c97-106">![WMI 錯誤訊息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 錯誤訊息")</span><span class="sxs-lookup"><span data-stu-id="64c97-106">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="64c97-107">若您未安裝 WMI 回溯相容性套件，而嘗試啟動 **Merge-CsLegacytopology** Cmdlet，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="64c97-107">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="64c97-108">![Windows PowerShell WMI 提供者錯誤](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供者錯誤")</span><span class="sxs-lookup"><span data-stu-id="64c97-108">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="64c97-109">安裝 WMI 回溯相容性套件</span><span class="sxs-lookup"><span data-stu-id="64c97-109">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="64c97-110">從安裝媒體，流覽至 \\ setup \\ AMD64 \\ 安裝 \\OCSWMIBC.MSI。</span><span class="sxs-lookup"><span data-stu-id="64c97-110">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="64c97-111">安裝 OCSWMIBC.MSI。</span><span class="sxs-lookup"><span data-stu-id="64c97-111">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64c97-p101">OCSWMIBC.msi 必須安裝在執行 [拓撲產生器合併精靈] 的電腦上。然而，建議將 OCSWMIBC.msi 安裝在拓撲中的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="64c97-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64c97-114">OCSWMIBC.msi 可以安裝在已安裝 Lync Server 2013 核心元件和 Lync Server 2013 管理命令介面的網域中的任何電腦上，而且可以存取 Office 通訊伺服器 2007 R2 拓撲 (WMI 提供者) 和 SQL Server) 中的 Active Directory 網域服務 (。</span><span class="sxs-lookup"><span data-stu-id="64c97-114">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

