---
title: Lync Server 2013：執行非正式的語音路由測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>在 Lync Server 2013 中執行非正式語音路由測試

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

您可以在建立實際測試案例前，使用 [**建立語音路由測試案例資訊**] 對話方塊來執行非正式測試。 當您對測試結果感到滿意時，您可以選擇將它儲存為正式測試案例。

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>執行非正式的語音路由測試

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。

4.  在 [**測試語音路由**] 頁面上，按一下 [**建立語音路由測試案例資訊**]。

5.  在 [**撥入號碼**] 欄位中，輸入您要用於此測試的電話號碼。 這個數位將會正常化並顯示在 [**結果**] 窗格的 [**正常化數位**] 欄位中。

6.  在**撥號計畫**清單中，選取要用來測試撥入號碼的撥號計畫。 預設為全域撥號方案。
    
    當您執行測試時，在 [**結果**] 窗格的 [**正常化規則**] 欄位中，會顯示符合撥號號碼的第一個正常化規則。

7.  在 [**語音原則**] 清單中，選取要用來測試撥入號碼的語音原則。 預設為全域語音原則。
    
    當您執行測試時，此語音原則中的第一個相符 PSTN 使用記錄會顯示在 [**結果**] 窗格的**第一個 PSTN 使用**欄位中。 此外，與此 PSTN 使用記錄相關的第一個相符的語音路由會顯示在**第一個路由**欄位中。

8.  可選如果您想要針對指派給特定使用者的語音原則測試撥入號碼，請選取 [**填入使用者**] 核取方塊。
    
    1.  按一下 **[流覽]** 以顯示 [**選取企業語音使用者**] 對話方塊。
    
    2.  按一下 [**尋找**]，顯示已啟用企業語音的使用者清單。
    
    3.  按兩下您想要用於此測試的使用者名稱，其指派的語音原則。 **原則**欄位現在已填入指派給所選使用者的語音原則。
    
    當您執行測試時，此語音原則中的第一個相符公用電話網絡（PSTN）使用量記錄會顯示在 [**結果**] 窗格的**第一個 PSTN 使用**欄位中。 此外，與此 PSTN 使用記錄相關的第一個相符的語音路由會顯示在**第一個路由**欄位中。

9.  按一下 [**執行**] 以執行測試案例。 結果會顯示在對話方塊的右面板中。

10. 可選如果您想要將此測試設定儲存為正式測試案例，請按一下 [**另存**新格式]。
    
    1.  在 [**儲存語音路由測試案例資訊**] 對話方塊的 [**名稱**] 欄位中，輸入測試案例的唯一名稱。
        
        該名稱在企業語音部署中的所有語音路由測試案例中都必須是唯一的。 它最多可有32個字元，而且除了反斜線（\\）、句號（.）或底線（\_）之外，也可以包含任何字母數位字元。
    
    2.  請注意，[**儲存語音路由測試案例資訊**] 對話方塊上的剩餘欄位是唯讀的，且是從非正式測試設定*和*結果預填的。 確認這是您要儲存在測試案例中的設定。
        
        <div>
        

        > [!NOTE]  
        > 來自測試結果的值會用於在 [<STRONG>儲存語音路由測試案例資訊</STRONG>] 對話方塊上預填欄位，如下所示： 
        > <UL>
        > <LI>
        > <P>[<STRONG>預期的翻譯</STRONG>] 會預先填入 [<STRONG>正常化數位</STRONG>] 欄位中的值。</P>
        > <LI>
        > <P>[<STRONG>預期的路線</STRONG>] 會預先填入<STRONG>第一個 [路線</STRONG>] 欄位中的值。</P>
        > <LI>
        > <P><STRONG>預期的 pstn 使用記錄</STRONG>已預先填入<STRONG>第一個 pstn 使用量</STRONG>欄位中的值。</P></LI></UL>如果在測試執行期間找不到這些值的相符，則 [<STRONG>儲存語音路由測試案例資訊</STRONG>] 對話方塊上的對應欄位會是空的。

        
        </div>
    
    3.  按一下 **[確定]** 以儲存測試案例，或按一下 [**取消**] 以回到 [**查看語音路由測試案例資訊**] 對話方塊，在儲存前，進一步開發測試。

11. 按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立語音路由測試案例時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈測試案例。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立語音路由測試案例](lync-server-2013-create-a-voice-routing-test-case.md)  
[在 Lync Server 2013 中執行語音路由測試案例](lync-server-2013-run-voice-routing-test-cases.md)  
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

