---
title: Lync Server 2013：強制執行電話鎖定
description: Lync Server 2013：強制執行電話鎖定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575599"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>在 Lync Server 2013 中強制執行電話鎖定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

出於安全性目的，可鎖定 Lync Phone Edition 裝置。 如果您強制執行電話鎖定，則執行 Lync Phone Edition 的裝置會在您設定的一段時間後鎖定。 當電話鎖定時，使用者可以撥打電話，但無法存取行事曆和連絡人資訊、語音信箱或通話記錄或使用搜尋。 若要解除電話鎖定，使用者會輸入 PIN 碼。

若要強制執行電話鎖定，請使用 Lync Server 控制台或 Lync Server PowerShell Cmdlet 來啟用和設定。 您可以以全域方式或僅在設定它的網站內強制執行電話鎖定。

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>設定並強制執行電話鎖定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  依序按一下 **[用戶端]** 和 **[裝置設定]**。

4.  在 **[裝置設定]** 索引標籤的裝置設定清單中，按兩下您要變更電話鎖定設定的設定。

5.  在 **[編輯裝置設定]** 對話方塊中，確認已選取 **[強制執行裝置鎖定]** 核取方塊。

6.  在 [ **最小 PIN 碼長度**] 中，接受解除鎖定 PIN 必須包含或指定新值之位數下限的預設值。 PIN 碼的長度範圍是四到15位數，預設值為6。

7.  在 [ **電話鎖定**超時] 中，接受電話鎖定本身之前的最短時間長度的預設值，或指定新值。 超時的範圍是0到60分鐘，預設值為10。 輸入值，格式為 HH： MM： SS。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 強制進行電話鎖定

您可以使用 Set-CsUCPhoneConfiguration Cmdlet 強制執行電話鎖定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-phone-locking"></a>啟用電話鎖定

  - 下列命令可啟用 Redmond 網站的電話鎖定。 若要停用電話鎖定，請將 EnforcePhoneLock 屬性設為 ($False)。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>啟用電話鎖定及修改電話鎖定超時

  - 此命令可啟用電話鎖定，也可將電話鎖定逾時設為 30 分鐘。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>在整個組織中啟用電話鎖定

  - 在此範例中，組織中所使用的所有 UC 電話組態設定都啟用了電話鎖定。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

如需詳細資訊，請參閱 [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[管理 Lync Server 2013 驗證](lync-server-2013-managing-lync-server-authentication.md)  


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

