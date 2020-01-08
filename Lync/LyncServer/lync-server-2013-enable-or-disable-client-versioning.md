---
title: Lync Server 2013：啟用或停用用戶端版本設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a0f6e5306e30baca3c2a8178a0d979f82d55481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用用戶端版本設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本配置設定是用來開啟或關閉用戶端版本控制（全域或針對特定網站）。 全域用戶端版本設定會安裝 Lync Server 2013，並用於針對整個伺服器部署啟用或停用用戶端版本控制。 啟用全域設定之後，您所擁有的任何用戶端版本原則都會在使用者嘗試登入時生效。 如果您不想要發生任何用戶端版本控制，您可以停用全域用戶端版本設定。 您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 啟用或停用用戶端版本設定。

<div>


> [!NOTE]  
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 啟用或停用用戶端版本設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定] 瀏覽按鈕。

4.  請執行下列步驟：
    
      - 若要全域啟用或停用用戶端版本設定，請按兩下**全域**配置，然後修改設定。
    
      - 若要啟用或停用特定網站的用戶端版本設定，請按一下 [**新增**]，選取該網站，按一下 **[確定]**，然後修改該網站的設定。

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用或停用用戶端版本設定

您可以使用 CsClientVersionConfiguration Cmdlet 來啟用或停用用戶端版本**設定**。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-client-versioning"></a>啟用用戶端版本設定

  - 您可以將**Enabled**屬性設為 True （$True）來啟用用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>停用用戶端版本設定

  - 您可以將**Enabled**屬性設為 False （$False）來停用用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

如需詳細資訊，請參閱[CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

