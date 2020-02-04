---
title: 建立或修改 Lync 手機版配置設定的集合
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
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改 Lync 手機版配置設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

當您安裝 Lync Server 時，您會看到一組「Lync Phone Edition」設定的全域集合。 這些設定適用于在您的部署中執行 Lync Phone Edition 的所有裝置。 您可以隨時變更這些設定。 您也可以設定套用至特定網站中裝置的新設定集合。 [網站設定] 優先于 [全域設定]。

配置設定是由集合名稱、範圍（全域或網站）、SIP 安全性設定、記錄層級、語音服務品質（QoS）等級、電話封鎖設定和電話鎖定的詳細資料所組成（也就是 a）解除鎖定個人識別碼的時間（PIN）必須是與 b 的電話，才能自行鎖定。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>若要建立 Lync Phone Edition 配置設定的集合，或編輯現有收藏的設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置配置**] 瀏覽按鈕。

4.  在 [**裝置**設定] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的 Lync 手機版本設定，請按一下 [**新增**]，選取一個網站，按一下 **[確定]**，查看預設設定，並視需要進行變更。
    
      - 若要編輯現有集合中的任何設定，請按一下該集合，按一下 [**編輯**] 功能表，按一下 [**顯示詳細資料**]，然後進行您要的變更。
        
        <div>
        

        > [!TIP]
        > 若要返回使用全域集合的預設設定，請按一下全域集合，按一下 [<STRONG>編輯</STRONG>] 功能表，按一下 [<STRONG>刪除</STRONG>]，然後按一下<STRONG>[確定]</STRONG>。 這不會刪除全域集合;它只會將設定重設為預設值。

        
        </div>

5.  按一下 [認可]****。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來建立新的 Lync 手機版配置設定

您可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** Cmdlet，建立 Lync Phone Edition 設定設定（僅限在網站範圍內）。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>若要建立使用預設值的新 Lync 手機版配置設定

  - 這個命令會針對雷德蒙的網站建立一組新的 UC 手機設定：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>若要在建立新的 Lync Phone 版本設定時變更單一屬性值

  - 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立 UC 手機設定的集合，且根據預設，需要電話鎖定，請使用如下所示的命令：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>若要在建立新的 Lync Phone Edition 設定時變更多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會強制進行電話鎖定，也會將最小 PIN 長度設定為8位數：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

如需詳細資訊，請參閱[新 CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))。

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 中現有的 Lync Phone Edition 配置設定集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中強制執行電話鎖定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

