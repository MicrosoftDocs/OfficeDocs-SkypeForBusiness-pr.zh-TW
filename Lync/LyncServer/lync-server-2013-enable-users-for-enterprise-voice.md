---
title: Lync Server 2013：為使用者啟用企業語音
description: Lync Server 2013：為使用者啟用 Enterprise Voice。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa8dbbeb507ced5217e517c1608c3a2a9259668
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557649"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中啟用使用者的 Enterprise Voice

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在您安裝一或多個轉送伺服器的檔案、設定撥出電話路由，並選擇性地部署一或多個高級 Enterprise Voice 功能之後，您可以使用下列程式，讓使用者使用 Enterprise Voice 進行呼叫：

<div>


> [!NOTE]  
> 在下列程式中，只有先使用 Lync Server 控制台才能執行第一個程式。 其餘的程式，您只能使用 Lync Server 管理命令介面。



</div>

  - 啟用 Enterprise Voice 的使用者帳戶。

  -  (選用) 指派使用者特有的語音原則的使用者帳戶。

  -  (選用) 指派使用者特定撥號對應表的使用者帳戶。

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>啟用企業語音的使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。

5.  在表格中，按一下您要為 Enterprise Voice 啟用的使用者帳戶。

6.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

7.  在 [ **編輯 Lync Server 使用者** ] 頁面的 [ **電話**語音] 下，按一下 [ **企業語音**]。

8.  按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如，電話： + 14255550200) 。

9.  按一下 **[認可]**。

若要完成為使用者啟用 Enterprise Voice，請確定使用者已獲指派語音原則和撥號對應表，不論是預設指派的全域 () 或使用者特有的。

根據預設，會為所有使用者指派通用語音原則和撥號對應表。 如果語音原則或撥號對應表存在於使用者帳戶所在網站的網站層級上，這些網站原則將會自動套用至使用者。 若要將個別使用者的語音原則或撥號對應表套用至使用者，您必須執行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** Cmdlet。 如需詳細資訊，請參閱 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔。

</div>

<div>

## <a name="voice-policy-assignment"></a>語音原則指派

全域與網站層級語音原則會自動指派給所有已啟用 Enterprise Voice 的使用者帳戶。 您也可以建立適用于特定使用者或群組的語音原則。 這些每個使用者的原則都必須明確指派給使用者或群組。 如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站語音原則，您可以略過此區段，然後繼續本主題稍後的 [撥號對應表指派] 區段。

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>指派使用者特有的語音原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要將現有的使用者語音原則指派給使用者，請在命令提示字元中執行下列命令：
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **VoicePolicyJapan**的語音原則。

如需指派使用者特有語音原則或執行 **Grant-CsVoicePolicy** Cmdlet 的詳細資訊，請參閱 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔。

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>撥號對應表指派

若要為企業語音使用者或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指定撥號對應表。 當您未明確指派現有的個別使用者撥號對應表時，使用者帳戶會自動使用全域撥號對應表或網站層級撥號對應表（如果有的話）。 如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站撥號對應表，您可以略過本節。

<div>

## <a name="to-assign-a-dial-plan"></a>若要指派撥號對應表

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要指派使用者特有的撥號對應表，請在命令提示字元中執行下列命令：
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **DialPlanJapan**的使用者撥號對應表。

如需指派使用者撥號對應表或執行 **Grant-CsDialPlan** Cmdlet 的詳細資訊，請參閱 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[停用 Lync Server 2013 的 Enterprise Voice 使用者](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

