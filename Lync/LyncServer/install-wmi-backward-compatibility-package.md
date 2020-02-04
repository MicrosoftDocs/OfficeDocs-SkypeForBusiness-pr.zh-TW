---
title: 安裝 WMI 向後相容性套件
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
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="3e567-102">安裝 WMI 向後相容性套件</span><span class="sxs-lookup"><span data-stu-id="3e567-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e567-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3e567-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3e567-104">如果您嘗試執行拓撲建立器合併嚮導而不安裝 WMI 向後相容性套件，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="3e567-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="3e567-105">![WMI 錯誤訊息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 錯誤訊息")</span><span class="sxs-lookup"><span data-stu-id="3e567-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="3e567-106">如果您嘗試執行**Merge CsLegacytopology** Cmdlet 而不安裝 WMI 向後相容性套件，您會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="3e567-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="3e567-107">![Windows PowerShell WMI 提供者錯誤](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供者錯誤")</span><span class="sxs-lookup"><span data-stu-id="3e567-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="3e567-108">若要安裝 WMI 向後相容性套件</span><span class="sxs-lookup"><span data-stu-id="3e567-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="3e567-109">從您的安裝媒體，流覽\\至\\setup\\AMD64\\設定 OCSWMIBC。.MSI.</span><span class="sxs-lookup"><span data-stu-id="3e567-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="3e567-110">安裝 OCSWMIBC。.MSI.</span><span class="sxs-lookup"><span data-stu-id="3e567-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e567-111">OCSWMIBC 必須安裝在執行拓撲建立器合併嚮導的電腦上。</span><span class="sxs-lookup"><span data-stu-id="3e567-111">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run.</span></span> <span data-ttu-id="3e567-112">不過，我們建議您在拓撲中的所有前端伺服器上安裝 OCSWMIBC。</span><span class="sxs-lookup"><span data-stu-id="3e567-112">However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e567-113">在已安裝 Lync Server 2013 核心元件和 Lync Server 2013 管理命令介面的網域中，OCSWMIBC 可以安裝在任何電腦上，且能夠存取 Office 通訊伺服器 2007 R2 拓撲（WMI 提供者至 Active Directory 網域[服務（AD DS）] 和 [SQL Server]。</span><span class="sxs-lookup"><span data-stu-id="3e567-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

