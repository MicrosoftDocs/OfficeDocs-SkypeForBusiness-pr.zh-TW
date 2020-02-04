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

# <a name="install-wmi-backward-compatibility-package"></a>安裝 WMI 向後相容性套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

如果您嘗試執行拓撲建立器合併嚮導而不安裝 WMI 向後相容性套件，您會看到下列錯誤：

![WMI 錯誤訊息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 錯誤訊息")

如果您嘗試執行**Merge CsLegacytopology** Cmdlet 而不安裝 WMI 向後相容性套件，您會看到下列錯誤：

![Windows PowerShell WMI 提供者錯誤](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供者錯誤")

若要安裝 WMI 向後相容性套件

1.  從您的安裝媒體，流覽\\至\\setup\\AMD64\\設定 OCSWMIBC。.MSI.

2.  安裝 OCSWMIBC。.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC 必須安裝在執行拓撲建立器合併嚮導的電腦上。 不過，我們建議您在拓撲中的所有前端伺服器上安裝 OCSWMIBC。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 在已安裝 Lync Server 2013 核心元件和 Lync Server 2013 管理命令介面的網域中，OCSWMIBC 可以安裝在任何電腦上，且能夠存取 Office 通訊伺服器 2007 R2 拓撲（WMI 提供者至 Active Directory 網域[服務（AD DS）] 和 [SQL Server]。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

