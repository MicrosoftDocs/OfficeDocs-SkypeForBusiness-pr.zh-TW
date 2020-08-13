---
title: Lync Server 2013：開始將使用者從 Lync Online 遷移至 Lync 內部部署之前的第一個步驟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>在 Lync Server 2013 中開始將使用者從 Lync Online 遷移至 Lync 內部部署之前的第一個步驟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-08_

在您開始將 Lync Online 使用者移至您的內部部署環境之前，請檢查下列所有專案皆為真：

  - 您的 Lync Server 內部部署環境必須完全部署及驗證。 如需詳細資訊，請參閱[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

  - 您的 Lync Online 租使用者必須針對遠端 PowerShell 存取進行設定。
    
    若要這麼做，請先安裝適用于 Windows PowerShell 的 Lync Online 模組，您可以在這裡找到： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) 。
    
    安裝模組之後，您可以在 Lync Server 管理命令介面中輸入下列 Cmdlet 來建立遠端會話：
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    如需如何使用 Lync Online 建立遠端 PowerShell 會話的相關資訊，請參閱[使用 Windows PowerShell 連線到 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
    如需使用 Lync Online PowerShell 模組的詳細資訊，請參閱[使用 Windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

  - 您的 Lync Online 必須設定共用 SIP 位址空間。 若要這麼做，請先啟動與 Lync Online 的遠端 Powershell 會話。 然後執行下列 Cmdlet：
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

完成這些步驟之後，您可以在[Lync Server 2013 中，移至將 Lync Online 使用者遷移至 lync 內部部署](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。

</div>

<span> </span>

</div>

</div>

</div>

