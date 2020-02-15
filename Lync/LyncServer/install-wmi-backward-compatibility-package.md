---
title: 安裝 WMI 回溯相容性套件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2497fb60c4eeb0ef9bba499bd131ef6bba10f3ff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="1f02b-102">安裝 WMI 回溯相容性套件</span><span class="sxs-lookup"><span data-stu-id="1f02b-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f02b-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="1f02b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1f02b-104">若您未安裝 WMI 回溯相容性套件，而嘗試啟動 [拓撲產生器合併精靈]，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="1f02b-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="1f02b-105">![WMI 錯誤訊息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 錯誤訊息")</span><span class="sxs-lookup"><span data-stu-id="1f02b-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="1f02b-106">若您未安裝 WMI 回溯相容性套件，而嘗試啟動 **Merge-CsLegacytopology** Cmdlet，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="1f02b-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="1f02b-107">![Windows PowerShell WMI 提供者錯誤](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供者錯誤")</span><span class="sxs-lookup"><span data-stu-id="1f02b-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="1f02b-108">安裝 WMI 回溯相容性套件</span><span class="sxs-lookup"><span data-stu-id="1f02b-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="1f02b-109">從安裝媒體上，瀏覽至\\安裝\\AMD64\\安裝\\OCSWMIBC。MSI。</span><span class="sxs-lookup"><span data-stu-id="1f02b-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="1f02b-110">安裝 OCSWMIBC.MSI。</span><span class="sxs-lookup"><span data-stu-id="1f02b-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f02b-p101">OCSWMIBC.msi 必須安裝在執行 [拓撲產生器合併精靈] 的電腦上。然而，建議將 OCSWMIBC.msi 安裝在拓撲中的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1f02b-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f02b-113">可以在 Lync Server 2013 核心元件及 Lync Server 2013 管理命令介面安裝，且有權存取 Office Communications Server 2007 R2 拓撲 （WMI 提供者至 Active Directory 網域的網域中的任何電腦上安裝 OCSWMIBC.msi服務 (AD DS) 和 SQL Server)。</span><span class="sxs-lookup"><span data-stu-id="1f02b-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

