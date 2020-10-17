---
title: Lync Server 2013：查看 Lync Phone Edition 設定資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b613a8cd890b3c31028715a6eaac98462295602
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535740"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看 Lync Phone Edition 設定資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以查看有關執行 Lync Phone Edition 之裝置的設定資訊。 此資訊會組織成集合。 當您安裝 Lync Server 時，會取得 Lync Phone Edition 設定的集合，這些設定會套用至部署中所有執行 Lync Phone Edition 的裝置。 您也可以針對特定網站建立新的設定集合。 網站設定的優先順序高於全域設定。 每個設定集合都包含名稱、範圍 (全域或網站)、SIP 安全性設定、記錄層級、語音服務品質 (QoS) 層級、電話鎖定設定以及電話鎖定詳細資料 (也就是解除鎖定個人識別碼 (PIN) 的長度下限，以及電話自我鎖定之前的時間)。

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>若要查看有關執行 Lync Phone Edition 之裝置的設定資訊

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [用戶端]****，然後按一下 [裝置設定]**** 導覽按鈕。

4.  在「裝置設定」**** 頁面上，按一下您要檢視其相關資訊的設定集合。名稱、範圍、SIP 安全性設定、語音品質層級及電話鎖定設定會列示在主要頁面上。若要檢視記錄層級和電話鎖定詳細資料，請按一下 [編輯]**** 功能表，然後按一下 [顯示詳細資料]****。

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 Lync Phone Edition 設定資訊

您可以使用 Lync Server 管理命令介面和 **Get-CsUCPhoneConfiguration** Cmdlet 來查看 Lync Phone Edition 的設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>若要查看 Lync Phone Edition 設定資訊

  - 若要查看所有 Lync Phone Edition 設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsUCPhoneConfiguration
    
    該命令會傳回如下資訊：
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

如需詳細資訊，請參閱 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中強制執行電話鎖定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

