---
title: Lync Server 2013：允許 Lync 使用者進行遠端呼叫控制
description: Lync Server 2013：允許 Lync 使用者進行遠端呼叫控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84b76d0d899da8ca25f42b5bed450914890f4b27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559599"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Lync 使用者的遠端呼叫控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您可以使用以伺服器為基礎的帶內布建原則，設定遠端呼叫控制的 Lync 使用者。 您可以使用 Lync Server 控制台或 Lync Server 管理命令介面命令列介面，管理頻帶內布布布配設定。 這些工具會取代 Windows Management Instrumentation (WMI) 管理單元，用來管理舊版版本中的群組原則設定。

如果您想讓使用者在 Lync 中設定自己的遠端呼叫控制設定，您可以在不指定 **行伺服器 URI** 和 **行 URI** 值的情況下，在伺服器上設定使用者的遠端呼叫控制設定。 請務必向您的使用者傳達適當的 **線路伺服器 URI** 和 **行 URI** 值，並為您的使用者提供設定這些設定的指示。 如需在 Lync Server 中手動設定遠端呼叫控制的程式，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=210132> Microsoft Office 網站上的 Lync 用戶端檔中的「設定手機選項及號碼」。

如果您有現有的通訊伺服器 2007 R2 或通訊伺服器2007部署，Communicator 2007 R2 和 Communicator 2007 用戶端將在並排遷移期間繼續使用群組原則。 不過，如果您想要將原則設定傳送至 Lync 用戶端，您必須設定對等的 Lync Server 帶內布建設定。

<div>


> [!NOTE]  
> 若要讓使用者啟用遠端呼叫控制，您需要為使用者提供行 URI 和行伺服器 URI。 如在 <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 的遠端呼叫控制的部署</A>工作中所述，您必須確定使用閘道為這些設定所需的語法。<BR>當您設定靜態路由至閘道時，請確定行伺服器 URI 中的網域與您在 MatchUri 參數中指定的目的網域相同。<BR>行 URI 會指定以 e.164 格式指派給使用者的電話號碼，並使用 "TEL:" 首碼 (例如電話： + 14255550150) 。 如果您想要設定分機號碼，則該格式為電話： + 14255550150; ext = 111。 如果您先前已設定使用者的行 URI，但值尚未變更，則當您啟用使用者的遠端呼叫控制時，不需要指定行 URI。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>使用管理命令介面啟用啟用 Lync 功能之使用者的遠端呼叫控制

1.  登入安裝了 Lync Server 管理命令介面的電腦，做為 RTCUniversalServerAdmins 群組的成員，或是您已指派 **Set-CsUser** Cmdlet 的角色型存取控制角色。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要使用 **Set-CsUser** Cmdlet 設定現有啟用 Lync 功能之使用者的遠端呼叫控制，請執行下列操作：
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    例如：
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台設定遠端呼叫控制的使用者

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [ **搜尋使用者** ] 方塊中，輸入顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源 (識別碼的所有 (或第一個部分) ，然後按一下 [ **尋找**]。

5.  在表格中，按一下您要修改的使用者帳戶。

6.  在 **[編輯]** 功能表中，按一下 **[修改]**。

7.  在 [ **電話語音**] 中，執行下列其中一項操作：
    
      - 若要啟用遠端呼叫控制，讓使用者能夠控制其專用的分支用交換器 (PBX) Lync 2013 的電話，以進行 PC 對 PC 的音訊通話和 PC 對電話的通話，請按一下 [ **遠端呼叫控制**]。 在 [ **行 URI**] 中，指定使用者的電話號碼。 在 [ **行伺服器 URI**] 中，指定 SIP/CSTA 閘道的 SIP URI。
    
      - 若要啟用遠端呼叫控制，但是停用 PC 對 PC 音訊通話，並只讓使用者從 Lync 2013 控制其 PBX 電話，以進行 PC 對電話的通話，請按一下 [ **僅限遠端呼叫控制**]。 在 [ **行 URI**] 中，指定使用者的電話號碼。 在 [ **行伺服器 URI**] 中，指定 SIP/CSTA 閘道的 SIP URI。

8.  完成後，請按一下 [ **認可**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

