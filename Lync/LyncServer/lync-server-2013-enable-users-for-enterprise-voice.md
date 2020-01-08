---
title: Lync Server 2013：允許使用者使用企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中啟用企業語音的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在您安裝一或多個中繼伺服器的檔案之後，請設定輸出呼叫路由，以及選擇性地部署一或多個高級企業語音功能，您可以使用下列程式，讓使用者使用企業語音進行通話：

<div>


> [!NOTE]  
> 在下列程式中，只有第一個程式可以使用 Lync Server [控制台] 執行。 在其餘的程式中，您只能使用 Lync Server 管理命令介面。



</div>

  - 啟用企業語音的使用者帳戶。

  - 可選指派使用者帳戶專用的語音原則。

  - 可選將使用者帳戶指派給使用者專用的撥號方案。

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>啟用企業語音的使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5.  在表格中，按一下您要為企業語音啟用的使用者帳戶。

6.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

7.  在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**] 底下，按一下 [**企業語音**]。

8.  按一下 [**行 URI**]，然後輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。

9.  按一下 [認可]****。

若要為使用者啟用企業語音，請確定使用者已獲指派語音原則和撥號方案，不論全域（預設為指派）或使用者專用。

根據預設，所有使用者都會獲指派全域語音原則和撥號方案。 如果使用者帳戶所在網站的網站層級存在語音原則或撥號方案，這些網站原則將會自動套用至使用者。 若要將每個使用者的語音原則或撥號方案套用至使用者，您必須執行**授與 CsVoicePolicy**並**授與 CsDialPlan** Cmdlet。 如需詳細資訊，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。

</div>

<div>

## <a name="voice-policy-assignment"></a>語音原則指派

全域及網站層級語音原則會自動指派給所有已啟用企業語音的使用者帳戶。 您也可以建立適用于特定使用者或群組的語音原則。 這些每個使用者的原則必須明確指派給使用者或群組。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站語音原則，您可以略過此區段，然後繼續本主題稍後的撥號計畫作業區段。

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>指派使用者專用的語音原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要將現有的使用者語音原則指派給使用者，請在命令提示字元執行下列動作：
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    在這個範例中，使用顯示名稱 Bob 凱利的使用者會獲指派「名稱**VoicePolicyJapan**」的語音原則。

如需指派使用者特定語音原則或執行**Grant CsVoicePolicy** Cmdlet 的詳細資料，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>撥號方案指派

若要為企業語音或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指派撥號方案。 如果您不明確指派現有的每個使用者撥號方案，使用者帳戶就會自動使用全域撥號方案，或（如果有的話）。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站撥號方案，您可以略過本節。

<div>

## <a name="to-assign-a-dial-plan"></a>指派撥號方案

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要指派使用者特定的撥號方案，請在命令提示字元執行下列動作：
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    在這個範例中，使用顯示名稱 Bob 凱利的使用者會被指派名稱為**DialPlanJapan**的使用者撥號計畫。

如需指派使用者撥號方案或執行**授與 CsDialPlan** Cmdlet 的詳細資料，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中停用企業語音的使用者](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

