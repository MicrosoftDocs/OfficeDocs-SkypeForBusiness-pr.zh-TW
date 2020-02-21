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
ms.openlocfilehash: c59e3ea03b3b6f4085f8acf461b1da3f32e21fa9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>安裝 WMI 回溯相容性套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

若您未安裝 WMI 回溯相容性套件，而嘗試啟動 [拓撲產生器合併精靈]，您會看到下列錯誤：

![WMI 錯誤訊息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 錯誤訊息")

若您未安裝 WMI 回溯相容性套件，而嘗試啟動 **Merge-CsLegacytopology** Cmdlet，您會看到下列錯誤：

![Windows PowerShell WMI 提供者錯誤](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供者錯誤")

安裝 WMI 回溯相容性套件

1.  從安裝媒體上，瀏覽至\\安裝\\AMD64\\安裝\\OCSWMIBC。MSI。

2.  安裝 OCSWMIBC.MSI。
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi 必須安裝在執行 [拓撲產生器合併精靈] 的電腦上。然而，建議將 OCSWMIBC.msi 安裝在拓撲中的所有前端伺服器上。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 可以在 Lync Server 2013 核心元件及 Lync Server 2013 管理命令介面安裝，且有權存取 Office Communications Server 2007 R2 拓撲 （WMI 提供者至 Active Directory 網域的網域中的任何電腦上安裝 OCSWMIBC.msi服務 (AD DS) 和 SQL Server)。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

