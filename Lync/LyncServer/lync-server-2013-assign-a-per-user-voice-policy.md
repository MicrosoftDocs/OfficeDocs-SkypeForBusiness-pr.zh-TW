---
title: Lync Server 2013：指派每個使用者的語音原則
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
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723403"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的語音原則

 


全域及網站層級語音原則會自動指派給所有啟用企業語音的 Lync Server 2013 使用者帳戶。 您也可以使用 Lync Server 2013 的 [控制台] 或 [Lync Server 2013 管理命令介面]，將語音原則指派給特定的使用者。 使用本主題中的程式，將每個使用者的原則明確指派給 Lync Server 使用者。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>使用 Lync Server [控制台] 指派使用者專用的語音原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [**語音原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用 [預設伺服器] 或 [全域原則設定]。



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的語音原則

您可以使用 Windows PowerShell 和**Grant CsVoicePolicy** Cmdlet 指派每個使用者的語音原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>將每個使用者的語音原則指派給單一使用者

  - 下列命令會將每個使用者的語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>若要將每個使用者的語音原則指派給多個使用者

  - 這個命令會將每個使用者的語音原則 FinanceVoicePolicy 指派給在 Active Directory 的財務 OU 中擁有帳戶的所有使用者。 如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>若要取消指派每個使用者的語音原則

  - 下列命令會以前指派給 Ken Myer 的任何每使用者語音原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[Grant CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) Cmdlet 的說明主題。

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中停用企業語音的使用者](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)

