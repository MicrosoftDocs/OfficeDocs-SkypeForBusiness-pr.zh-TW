---
title: Lync Server 2013：強制執行電話鎖定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4961aabf2edce33f1e5975497844704ac0feae03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>在 Lync Server 2013 中強制執行電話鎖定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

出於安全性考慮，您可以鎖定 Lync 手機版裝置。 如果您強制執行電話鎖定，則在您設定的一段時間後，執行 Lync Phone Edition 的裝置會封鎖。 當手機鎖定時，使用者可以撥打電話，但無法存取行事曆和連絡人資訊、語音信箱或通話記錄，或使用搜尋。 若要解除鎖定電話，使用者可以輸入 PIN。

若要強制執行電話鎖定，請使用 Lync Server 的 [控制台] 或 [Lync Server PowerShell Cmdlet] 來啟用和設定。 您可以全域或只在其設定的網站中強制執行電話鎖定。

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>設定和強制執行電話鎖

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下 [**用戶端**]，然後按一下 [**裝置配置**]。

4.  在 [**裝置**設定] 索引標籤上，于裝置配置清單中，按兩下您要變更電話鎖定設定的配置。

5.  在 [**編輯裝置**設定] 對話方塊中，確認已選取 [**強制裝置鎖定**] 核取方塊。

6.  在 [**最小 PIN 長度**] 中，接受解除鎖定 PIN 必須包含或指定新值的最小位數數的預設值。 PIN 長度的範圍是4到15個數字，預設值是6。

7.  在 [**電話封鎖**超時] 中，接受手機鎖定本身或指定新值前的最短時間長度的預設值。 超時的範圍是0到60分鐘，而預設值為10。 以 HH： MM： SS 格式輸入值。

8.  按一下 [認可]****。

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 強制進行電話鎖定

您可以使用 CsUCPhoneConfiguration Cmdlet 來強制執行電話鎖定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-phone-locking"></a>啟用電話鎖定

  - 下列命令可讓雷德蒙網站的電話封鎖。 若要停用電話鎖定，請將 EnforcePhoneLock 屬性設定為 False （$False）。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>啟用電話封鎖及修改電話封鎖超時

  - 這個命令會啟用電話鎖定，同時也會將電話封鎖超時設定為30分鐘。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>若要在整個組織中啟用電話鎖定

  - 在這個範例中，在組織中使用的所有 UC 手機設定設定都已啟用電話鎖定。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

如需詳細資訊，請參閱[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[管理 Lync Server 2013 驗證](lync-server-2013-managing-lync-server-authentication.md)  


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

