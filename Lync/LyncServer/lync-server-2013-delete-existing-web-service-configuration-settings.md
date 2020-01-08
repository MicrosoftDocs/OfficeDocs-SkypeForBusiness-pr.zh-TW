---
title: Lync Server 2013：刪除現有的 Web 服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faecc3675e4ed22e6bab3a85825ae65c50a8511f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中的現有 Web 服務設定設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

請依照下列步驟刪除 web 服務設定。

<div>

## <a name="to-delete-web-service-configuration-settings"></a>刪除 web 服務配置設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **Web 服務**]。

4.  在 [ **Web 服務**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之原則的全部或部分名稱。

5.  在原則清單中，按一下您想要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 刪除 Web 服務配置設定

您可以使用 Windows PowerShell 與**Remove CsWebServiceConfiguration** Cmdlet 來刪除 web 服務設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>刪除 web 服務設定的特定集合

  - 下列命令會移除套用至雷德蒙網站的 Web 服務安全性設定：
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>若要刪除所有套用至網站範圍的 web 服務設定設定

  - 下列命令會移除所有套用至服務範圍的 Web 服務安全性設定：
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>若要刪除所有允許憑證驗證的 web 服務設定設定

  - 下列命令會移除所有允許使用憑證驗證的 Web 服務安全性設定：
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

如需詳細資訊，請參閱[移除-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 [控制台] 中設定驗證](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

