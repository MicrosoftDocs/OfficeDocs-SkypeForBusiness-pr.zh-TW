---
title: 建立或修改 Lync Phone Edition 配置設定的集合
description: 建立或修改 Lync Phone Edition 配置設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578249"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

當您安裝 Lync Server 時，會取得「Lync Phone Edition」設定的全域集合。 這些設定會套用至部署中所有執行 Lync Phone Edition 的裝置。 您可以隨時變更這些設定。 您也可以設定套用至特定網站中裝置的新設定集合。 網站設定的優先順序高於全域設定。

組態設定包含集合名稱、範圍 (全域或網站)、SIP 安全性設定、記錄層次、語音服務品質 (QoS) 層級、電話鎖定設定與電話鎖定詳細資料，即 a) 個人識別碼 (PIN) 的解除鎖定時間必須為多久，以及 b) 電話自行鎖定前的閒置時間為多久。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>若要建立 Lync Phone Edition 設定的集合，或編輯現有集合的設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[用戶端]**，然後再按一下 **[裝置組態]** 導覽按鈕。

4.  在 **[裝置組態]** 頁面上，執行下列其中一項作業：
    
      - 若要建立新的 Lync Phone Edition 設定的集合，請依序按一下 [ **新增**] 及 **[網站]，按一下 [確定]**，複查預設設定，如果您想要的話，請進行任何變更。
    
      - 若要在現有集合中編輯任何設定，請依序按一下集合、**[編輯]** 功能表、**[顯示詳細資料]**，然後進行變更。
        
        <div>
        

        > [!TIP]
        > 若要返回以使用全域集合的預設設定，請依序按一下全域集合、<STRONG>[編輯]</STRONG>功能表、<STRONG>[刪除]</STRONG>，然後按一下 <STRONG>[確定]</STRONG>。這樣做並不會刪除全域集合，只是將設定重設為預設值。

        
        </div>

5.  按一下 **[認可]**。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立新的 Lync Phone Edition 配置設定

您可以在網站範圍內 (，只) 使用 Windows PowerShell 和 **New-CsUCPhoneConfiguration** Cmdlet 來建立 Lync Phone Edition 的設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>若要建立新的 Lync Phone Edition 設定，使用預設值

  - 這個命令會針對 Redmond 網站建立一組新的 UC 電話組態設定：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    由於以上的命令未指定任何參數 (強制的 Identity 參數除外)，新的組態設定集合將針對其所有屬性使用預設值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>在建立新的 Lync Phone Edition 配置設定時變更單一屬性值

  - 若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。例如，若要建立 UC 電話組態設定的集合，根據預設，需要執行電話鎖定，您可以使用下列命令：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>在建立新的 Lync Phone Edition 配置設定時變更多個屬性值

  - 多項屬性值可透過加入多個參數加以修改。例如，這個命令會強制執行電話鎖定，也會將最小 PIN 長度限制設為 8 位數：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

如需詳細資訊，請參閱 [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中強制執行電話鎖定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

