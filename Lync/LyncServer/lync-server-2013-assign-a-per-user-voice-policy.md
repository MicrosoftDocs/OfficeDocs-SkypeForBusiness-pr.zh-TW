---
title: Lync Server 2013：指派每位使用者的語音原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943926"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每位使用者的語音原則

 


全域與網站層級語音原則會自動指派給所有啟用 Enterprise Voice 的 Lync Server 2013 使用者帳戶。 您也可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將語音原則指派給特定使用者。 使用本主題中的程式，將每一使用者原則明確指派給 Lync Server 使用者。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>使用 Lync Server 控制台指派使用者特有的語音原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [**語音原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。
    

    > [!NOTE]  
    > <STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器或全域原則設定。



## <a name="assign-per-user-voice-policies"></a>指派每位使用者的語音原則

您可以使用 Windows PowerShell 和**Grant-CsVoicePolicy** Cmdlet 指派每位使用者的語音原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 若要瞭解如何使用遠端 Windows PowerShell 連接至 Lync Server，請閱讀此 Lync Server Windows PowerShell 博客文章：[快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)。

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>將每一使用者語音原則指派給單一使用者

  - 下列命令會將每位使用者的語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>將每一使用者語音原則指派給多位使用者

  - 這個命令會將個別使用者的語音原則 FinanceVoicePolicy 指派給在 Active Directory 之財務 OU 中具有帳戶的所有使用者。 如需此命令中所使用之 OU 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>取消指派個別使用者的語音原則

  - 下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者語音原則。 一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。 網站原則優先順序高於全域原則。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱


[停用 Lync Server 2013 的 Enterprise Voice 使用者](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)

