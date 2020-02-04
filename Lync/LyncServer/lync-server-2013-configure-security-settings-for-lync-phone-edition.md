---
title: Lync Server 2013：設定 Lync Phone Edition 的安全性設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

透過您的 SIP 安全性設定和電話鎖定設定，協助改善執行 Lync 手機版本之裝置的安全性。

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>若要設定 Lync Phone Edition 的安全性設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置**設定]。

4.  在 [**裝置**設定] 頁面上，于裝置配置清單中，按兩下您要變更其安全性設定的配置。

5.  在 [**編輯裝置**設定] 的 [ **sip 安全性**] 中，指定 sip 安全等級。 預設層級為 [**高**]，我們建議使用它。

6.  在 [**編輯裝置**設定] 的 [**電話封鎖**] 底下，選取或清除 [**強制裝置鎖定**] 核取方塊（預設為選取），並指定最小 PIN 長度（預設為6個字元）和超時期間（預設為10分鐘）。 我們建議您使用這些預設值，或增加 PIN 長度及/或減少超時時間。
    
    <div>
    

    > [!NOTE]  
    > 如需詳細資訊，請參閱<A href="lync-server-2013-enforce-phone-locking.md">在 Lync Server 2013 中強制執行電話封鎖</A>。

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 設定 Lync Phone Edition 手機的安全性設定

您可以使用 Lync Server 管理命令介面和**CsUCPhoneConfiguration** Cmdlet 來管理安全性設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-modify-the-sip-security-mode"></a>修改 SIP 安全模式

  - 這個命令會將 UC 手機設定的全域集合的 SIPSecurityMode 設定為 [中]。 SIP 安全性也可以設定為 [低] 或 [高] （預設值）。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>若要修改最小 PIN 長度

  - 在這個範例中，所有的 UC 電話設定都經過修改，以要求最小 PIN 長度為7位數。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

如需詳細資訊，請參閱[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。

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

