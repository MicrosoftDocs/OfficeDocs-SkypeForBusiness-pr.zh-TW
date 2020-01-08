---
title: Lync Server 2013：建立語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>在 Lync Server 2013 中建立語音路由測試案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>建立測試案例

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。

4.  在 [**測試語音路由**] 頁面上，按一下 [**新增**] 以建立新的測試案例。

5.  在 [**名稱**] 中，輸入測試案例的唯一名稱。
    
    該名稱在企業語音部署中的所有語音路由測試案例中都必須是唯一的。 它最多可有32個字元，而且除了反斜線（\\）、句號（.）或底線（\_）之外，也可以包含任何字母數位字元。

6.  在 [撥入的**號碼**] 中，輸入您要用來測試您針對此測試案例指定之路由設定的撥號號碼。 根據撥號方案、路由及語音原則，這個數位將會正常化並顯示為輸出。

7.  在**撥號計畫**清單中，選取執行測試時要使用的撥號計畫。 預設為全域撥號方案。

8.  在 [**語音原則**] 清單中，選取執行測試時要使用的語音原則。 預設為全域語音原則。

9.  在 [**預期翻譯**] 中，以您想要在翻譯後看到的格式輸入電話號碼。 這是您在已選取的撥號方案中符合的第一個正常化規則所轉譯之後所測試之電話號碼的值。 當您執行測試案例時，如果您要測試的數位不會產生**預期轉譯**中的值，測試就會失敗。

10. 可選在 [**預期 PSTN 使用量**] 清單中，您可以根據指定的撥號方案和語音原則，選取您在執行測試案例時預期要使用的公用交換電話網絡（PSTN）使用記錄。 如果使用不同的 PSTN 使用記錄，測試就會失敗。

11. 可選在 [**預期的路線**] 清單中，您可以根據指定的撥號方案和語音原則，選取您在執行測試案例時預期要使用的語音路線。 如果使用不同的語音路由，測試就會失敗。

12. 可選按一下 [**執行**] 以執行測試案例。 結果會顯示在頁面的右側面板中。

13. 按一下 [確定]****。

14. 按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立語音路由測試案例時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>
    
    如果在測試中使用的撥號方案是正常化以加號（例如 + 12065551219）開頭的電話號碼，該方案可能會造成語音路由測試失敗。 （撥號規劃和語音路由都可以運作; 事實上，測試 CsDialPlan 會成功。 不過，語音路由測試可能失敗。在測試語音路由時，請務必記住這一點。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中匯出語音路由測試案例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中改善語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  


[在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

