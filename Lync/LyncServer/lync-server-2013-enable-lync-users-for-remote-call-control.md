---
title: Lync Server 2013：允許 Lync 使用者進行遠端呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中允許 Lync 使用者進行遠端呼叫控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您可以使用以伺服器為基礎的帶內提供原則，為遠端呼叫控制設定 Lync 使用者。 您可以使用 Lync Server [控制台] 或 [Lync Server Management Shell] 命令列介面，管理頻帶內的提供設定。 這些工具會取代在舊版版本中用來管理群組原則設定的 Windows 管理工具（WMI）管理單元。

如果您想讓使用者在 Lync 中設定自己的遠端呼叫控制設定，您可以為伺服器上的使用者設定遠端通話控制設定，而不需指定**行伺服器 URI**和**行 URI**值。 請務必向您的使用者傳達適當的**線路伺服器 URI**與**行 uri**值，並為您的使用者提供設定這些設定的指示。 如需在 Lync Server 中手動設定遠端通話控制的程式，請參閱 Microsoft Office 網站上的 Lync <http://go.microsoft.com/fwlink/p/?linkid=210132>用戶端檔中的「設定手機選項和號碼」。

如果您有現有的通訊伺服器 2007 R2 或通訊伺服器2007部署，Communicator 2007 R2 和 Communicator 2007 用戶端將在並排遷移期間繼續使用 [群組原則]。 不過，如果您想要將原則設定傳送到 Lync 用戶端，您必須設定對等的 Lync Server 內建配設設定。

<div>


> [!NOTE]  
> 若要讓使用者能夠進行遠端通話控制，您必須為使用者提供 Line URI 和 Line Server URI。 如在<A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中的遠端通話控制部署</A>工作中所述，您必須務必使用閘道在這些設定中所需的語法。<BR>當您將靜態路由設定至閘道時，請確定線路伺服器 URI 中的網域與您在 MatchUri 參數中指定的目標網域相同。<BR>Line URI 會以164格式指定指派給使用者的電話號碼，並使用 "電話：" 前置詞（例如電話： + 14255550150）。 如果您想要設定分機號碼，則該格式為電話： + 14255550150; ext = 111。 如果您先前已設定使用者的行 URI，而值並未變更，則當您啟用遠端通話控制的使用者時，不需要指定行 URI。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>使用管理命令介面為啟用 Lync 的使用者啟用遠端通話控制

1.  登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已指派**move-csuser** Cmdlet 的角色型存取控制角色。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要使用**move-csuser** Cmdlet 來設定現有 Lync 啟用的使用者的遠端通話控制，請執行下列動作：
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    例如：
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 設定遠端通話控制的使用者

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部（或第一個部分），然後按一下 [**尋找**]。

5.  在表格中，按一下您要修改的使用者帳戶。

6.  按一下 [**編輯**] 功能表上的 [**修改**]。

7.  在 [**電話**] 中，執行下列其中一項操作：
    
      - 若要啟用遠端呼叫控制，讓使用者從 Lync 2013 控制其私人分支 exchange （PBX）電話，以進行 PC 對電腦音訊通話和 PC 對電話的通話，請按一下 [**遠端通話控制**]。 在 [**行 URI**] 中，指定使用者的電話號碼。 在 [ **Line SERVER URI**] 中，指定 SIP/CSTA 閘道的 sip URI。
    
      - 若要啟用遠端通話控制，但停用 PC 對 PC 音訊通話，且要只讓使用者從 Lync 2013 控制其 PBX 手機，以進行 PC 到電話的通話，請按一下 [**僅限遠端通話控制**]。 在 [**行 URI**] 中，指定使用者的電話號碼。 在 [ **Line SERVER URI**] 中，指定 SIP/CSTA 閘道的 sip URI。

8.  完成後，請按一下 [ **Commit**] （提交）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

