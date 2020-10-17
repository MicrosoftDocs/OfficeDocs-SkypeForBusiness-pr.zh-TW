---
title: Lync Server 2013： View client version configuration 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec472bff967bc2a8ffb75d09e3515654487be41
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506600"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看用戶端版本設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會以 Lync Server 2013 進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。 啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。 您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，查看用戶端版本設定設定。

<div>


> [!NOTE]  
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台查看用戶端版本設定設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本** 設定] 導覽按鈕。

4.  按兩下您要查看之用戶端版本設定的名稱。

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看用戶端版本設定設定

您可以使用 **Get-CsClientVersionConfiguration** Cmdlet 來查看用戶端版本設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-client-version-configuration-information"></a>若要查看用戶端版本設定資訊

  - 若要查看所有用戶端版本設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsClientVersionConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

如需詳細資訊，請參閱 [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

