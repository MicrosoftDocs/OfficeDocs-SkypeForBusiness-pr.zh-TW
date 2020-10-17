---
title: Lync Server 2013：執行語音路由測試案例
description: Lync Server 2013：執行語音路由測試案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566789"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中執行語音路由測試案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

您可以執行語音路由測試案例套件中的所有測試案例，也可以執行一個或多個選取的測試案例。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>若要執行所有語音路由測試案例

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，依序按一下 **[語音路由]** 和 **[測試語音路由]**。

4.  在 [ **測試語音路由** ] 頁面上，按一下 [ **動作** ]，然後按一下 [ **全部執行**]。
    
    每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [ **通過/失敗** ] 欄中。 如果測試案例尚未執行，N/A 會顯示在 [ **通過/失敗** ] 欄中。

5.   (選用) 若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。 結果會顯示在 [ **編輯測試案例** ] 頁面右邊的陰影區域中：
    
    1.  **測試結果：** 測試案例執行的整體通過或失敗狀態。
    
    2.  正規化**規則：** 為此測試案例選取的撥號對應表中符合撥號號碼的第一個正規化規則 (數值**to test** field) 。
    
    3.  **正規化數目：** 正規化規則轉譯之後的撥號號碼值。
    
    4.  **第一個 PSTN 使用方式：** 為此測試案例選取的語音原則中，第一部公用交換電話網路 (PSTN) 使用方式記錄符合撥號號碼。
    
    5.  **第一個路由：** 第一個 PSTN 使用方式記錄中符合撥號號碼的第一個語音路由。
        
        <div>
        

        > [!NOTE]  
        > <STRONG>預期的 PSTN 使用方式記錄</STRONG>和<STRONG>預期路由</STRONG>欄位在語音路由測試案例設定中是選用的。 如果測試案例未指定這些值，測試結果中的對應欄位將會是空的。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>若要執行一或多個選取的語音路由測試案例

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **測試語音路由**]。

4.  在 [ **測試語音路由** ] 頁面上，按一下您要執行的測試案例名稱。

5.  在 [ **動作** ] 功能表上，按一下 [ **執行選取**的]。
    
    每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [ **通過/失敗** ] 欄中。 如果測試案例尚未執行，N/A 會顯示在 [ **通過/失敗** ] 欄中。

6.   (選用) 若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。 結果會顯示在 [ **編輯測試案例** ] 頁面右邊的陰影區域中：
    
    1.  **測試結果：** 測試案例執行的整體通過或失敗狀態。
    
    2.  正規化**規則：** 為此測試案例選取的撥號對應表中符合撥號號碼的第一個正規化規則 (數值**to test** field) 。
    
    3.  **正規化數目：** 正規化規則轉譯之後的撥號號碼值。
    
    4.  **第一個 PSTN 使用方式：** 為此測試案例選取的語音原則中符合撥號號碼的第一個 PSTN 使用方式記錄。
    
    5.  **第一個路由：** 第一個 PSTN 使用方式記錄中符合撥號號碼的第一個語音路由。
        
        <div>
        

        > [!NOTE]  
        > <STRONG>預期的 PSTN 使用方式記錄</STRONG>和<STRONG>預期路由</STRONG>欄位在語音路由測試案例設定中是選用的。 如果測試案例未指定這些值，測試結果中的對應欄位將會是空的。

        
        </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
[在 Lync Server 2013 中執行語音路由測試](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

