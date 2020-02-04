---
title: Lync Server 2013：查看 PIN 原則 inforrmation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f63b2abcc1278211b70fd575bbead8ae875332
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>在 Lync Server 2013 中查看 PIN 原則 inforrmation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 [**釘選原則**] 索引標籤來查看使用 IP 電話連線至 Lync 2013 之使用者的個人識別碼（PIN）驗證。 若要使用 PIN 驗證，請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中修改現有的 Web 服務配置設定](lync-server-2013-modify-existing-web-service-configuration-settings.md)。

請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中查看 PIN 原則的相關資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。

4.  在 [ **PIN 原則**] 頁面上，按一下原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 PIN 原則

您也可以使用 Windows PowerShell 和 CsPinPolicy Cmdlet 來查看 PIN 原則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-pin-policies"></a>若要查看 PIN 原則

  - 若要查看所有 PIN 原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsPinPolicy
    
    這會傳回如下所示的資訊：
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

如需詳細資訊，請參閱[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中修改現有的 Web 服務配置設定](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[在 Lync Server 2013 中建立新的 PIN 原則](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

