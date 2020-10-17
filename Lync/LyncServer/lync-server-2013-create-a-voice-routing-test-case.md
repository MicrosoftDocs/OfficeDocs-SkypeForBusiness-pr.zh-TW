---
title: Lync Server 2013：建立語音路由測試案例
description: Lync Server 2013：建立語音路由測試案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d81f4d39a6e3972ebf036fdaca59936f3f6b86bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562399"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>在 Lync Server 2013 中建立語音路由測試案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>建立測試案例

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，依序按一下 **[語音路由]** 和 **[測試語音路由]**。

4.  在 **[測試語音路由]** 頁面上，按一下 **[新增]** 建立新的測試案例。

5.  在 **[名稱]** 欄位中，輸入測試案例的唯一名稱。
    
    在您的企業語音部署中，所有語音路由測試案例的名稱都必須是唯一的。 它的長度最多為32個字元，而且可以包含任何字母元字元，除了反斜線 (\\) 、句點 ( ) 或底線 (\_) 。

6.  在 **[要測試的撥號號碼]** 欄位中，輸入要用來測試您為此測試案例指定的路由設定的撥號號碼。根據撥號對應表、路由和語音原則，此號碼會正規化並顯示為輸出。

7.  在 **[撥號對應表]** 清單中，選取執行測試時要使用的撥號對應表。預設是 [全域] 撥號對應表。

8.  在 **[語音原則]** 清單中，選取執行測試時要使用的語音原則。預設是通用語音原則。

9.  在 **[預期的轉譯]** 欄位中，以您希望在轉譯後看到的格式輸入電話號碼。這是在將電話號碼由所選撥號對應表中第一個符合的正規化規則轉譯之後，您會測試的電話號碼值。當您執行測試案例時，如果您測試的號碼未產生 **[預期的轉譯]** 欄位中的值，表示測試失敗。

10. (選用) 在 **[預期的 PSTN 使用方式]** 清單中，您可以根據指定的撥號對應表和語音原則，選取您執行測試案例時預期使用的 PSTN 使用方式記錄。如果使用不同的 PSTN 使用方式記錄，測試會失敗。

11. (選用) 在 **[預期的路由]** 清單中，您可以根據指定的撥號對應表和語音原則，選取您執行測試案例時預期使用的語音路由。如果使用不同的語音路由，測試會失敗。

12. (選用) 按一下 **[執行]** 來執行測試案例。結果會顯示在頁面的右側面板中。

13. 按一下 **[確定]**。

14. 依序按一下 **[認可]** 和 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立語音路由測試案例時，您必須執行 <STRONG>[全部認可]</STRONG> 命令來發行組態變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>
    
    如果測試中所使用的撥號對應表會正規化以加號 (開頭的電話號碼（例如 + 12065551219) ），該方案可能會導致語音路由測試失敗。  (撥號對應表，且語音路由會正常運作;實際上，Test-CsDialPlan 會成功。 不過，語音路由測試可能會失敗。 ) 這是在測試語音路由時必須記住的事項。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中匯出語音路由測試案例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中匯入語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  


[在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

