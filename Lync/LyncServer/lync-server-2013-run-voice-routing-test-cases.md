---
title: Lync Server 2013：執行語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中執行語音路由測試案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

您可以在語音路由測試案例套件中執行所有測試案例，或執行一或多個選取的測試案例。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>若要執行所有語音路由測試案例

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。

4.  在 [**測試語音路由**] 頁面上，按一下 [**動作**]，然後按一下 [**全部執行**]。
    
    每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [**通過/失敗**] 欄中。 如果測試案例還沒有執行，則 [**傳遞/失敗**] 欄中會顯示 [暫缺]。

5.  可選若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。 結果會顯示在 [**編輯測試案例**] 頁面右側的陰影區域中：
    
    1.  **測試結果：** 測試案例執行的整體階段或失敗狀態。
    
    2.  **正常化規則：** 針對此測試案例選取的撥號計畫中的第一個正常化規則，符合撥號號碼（[**要測試的號碼**] 欄位中的值）。
    
    3.  已**正常化的數位：** 在正常化規則轉譯之後所撥號碼的值。
    
    4.  **第一個 PSTN 使用量：** 在針對此測試案例所選取的語音原則中，第一個與撥號號碼相符的公用交換電話網絡（PSTN）使用量記錄。
    
    5.  **第一個路線：** 第一個與撥號號碼相符的 PSTN 使用量記錄中的第一個語音路線。
        
        <div>
        

        > [!NOTE]  
        > 在語音路由測試案例設定中，<STRONG>預期的 PSTN 使用記錄</STRONG>和<STRONG>預期路由</STRONG>欄位是選擇性的。 如果測試案例沒有指定這些值，測試結果中的對應欄位就會是空白的。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>執行一或多個選取的語音路由測試案例

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。

4.  在 [**測試語音路由**] 頁面上，按一下您要執行的測試案例的名稱。

5.  在 [**動作**] 功能表上，按一下 [**執行選取**的]。
    
    每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [**通過/失敗**] 欄中。 如果測試案例還沒有執行，則 [**傳遞/失敗**] 欄中會顯示 [暫缺]。

6.  可選若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。 結果會顯示在 [**編輯測試案例**] 頁面右側的陰影區域中：
    
    1.  **測試結果：** 測試案例執行的整體階段或失敗狀態。
    
    2.  **正常化規則：** 針對此測試案例選取的撥號計畫中的第一個正常化規則，符合撥號號碼（[**要測試的號碼**] 欄位中的值）。
    
    3.  已**正常化的數位：** 在正常化規則轉譯之後所撥號碼的值。
    
    4.  **第一個 PSTN 使用量：** 針對此測試案例所選取的語音原則中，符合撥入號碼的第一個 PSTN 使用記錄。
    
    5.  **第一個路線：** 第一個與撥號號碼相符的 PSTN 使用量記錄中的第一個語音路線。
        
        <div>
        

        > [!NOTE]  
        > 在語音路由測試案例設定中，<STRONG>預期的 PSTN 使用記錄</STRONG>和<STRONG>預期路由</STRONG>欄位是選擇性的。 如果測試案例沒有指定這些值，測試結果中的對應欄位就會是空白的。

        
        </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
[在 Lync Server 2013 中執行語音路由測試](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

