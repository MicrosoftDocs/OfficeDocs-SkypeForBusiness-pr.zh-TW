---
title: Lync Server 2013：修改語音路線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中修改語音路線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

本主題說明如何編輯語音路線。 若要建立新的路線，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。

<div>

## <a name="to-modify-a-voice-route"></a>修改語音路線

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**傳送**]。

4.  在 [**工藝路線**] 頁面上，使用下列其中一種方法來修改語音路線：
    
      - 按一下語音路由名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 按一下語音路由名稱，按一下 [**編輯**]，按一下 [**複製**]，然後按一下 [**貼**上]。 按一下您剛建立的語音信箱新複本，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯語音路線**] 頁面上的 [**名稱**] 欄位中，輸入語音路線的描述性名稱。

6.  可選在 [**描述**] 欄位中，輸入語音路線的其他描述性資訊。

7.  若要指定您想要此路由容納的模式，您可以使用 [**建立模式搭配**工具] 來產生正則運算式，或是手動撰寫正則運算式。
    
      - 若要使用 [**建立模式以搭配**工具] 來產生正則運算式，請輸入如下所示的值。 您可以指定兩種模式相符類型：
        
          - **您想要允許的數位起始位數：** 輸入此路由必須容納的首碼值（包括前置 + 視需要）。 例如，輸入 **+ 425** ，然後按一下 [**新增**]。 針對您想要包含在路線中的每一個前置詞值，重複此步驟。
        
          - **例外狀況：** 如果您想要指定一個或多個 [前置詞] 值的例外狀況，請醒目提示 [首碼]，然後按一下 [**例外**]。 針對您*不*想要此路線容納的相符模式，輸入一或多個值。 例如，若要從路由中排除從 + 425237 開始的數位，請在 [**例外**] 欄位中輸入 **+ 425237**的值，然後按一下 **[確定]**。
    
      - 若要手動定義 [相符] 模式，請按一下 [**組建符合**工具的模式] 中的 [**編輯**]，然後輸入 .net Framework 一般運算式，以指定要套用路線之目的地電話號碼的相符模式。 如需如何撰寫正則運算式的相關資訊，請參閱 ".NET Framework 正[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)則運算式"。

8.  如果您不想讓撥出通話的電話號碼出現在通話收件者，請選取 [**取消來電**顯示]。 如果您選取此選項，您必須指定將出現在收件者的本機號碼中的**替代呼叫者 id** 。

9.  若要將一或多個公開交換的電話網絡（PSTN） trunks 與語音路線關聯，請按一下 [**新增**]，然後從清單中選取主幹。
    
    <div>
    

    > [!NOTE]  
    > 如果您的部署包含任何 Microsoft Office 通訊伺服器 2007 R2 轉送伺服器，則也會出現在清單中。

    
    </div>

10. 若要將一或多個 PSTN 使用方式與語音路由建立關聯，請按一下 [**選取**]，然後從針對您的企業語音部署定義的 PSTN 使用狀況記錄清單中選擇記錄。
    
    <div>
    

    > [!NOTE]  
    > 若要查看每個可用 PSTN 使用量記錄的屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用狀況記錄</A>。<BR>若要建立或編輯 PSTN 使用記錄，請參閱<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中建立語音原則和設定 pstn 使用記錄</A>，或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">修改語音原則以及在 Lync server 2013 中設定 pstn 使用記錄</A>。

    
    </div>

11. 排列 PSTN 使用狀況記錄，以獲得最佳效能。 若要變更記錄在清單中的位置，請醒目提示記錄名稱，然後按一下向上或向下箭號。
    
    <div>
    

    > [!NOTE]  
    > 相對於語音原則，其中列出 PSTN 使用記錄的順序非常重要，因此語音路由中的 PSTN 使用記錄順序不是多餘的。 不過，我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。 （Lync Server 會從上到下遍歷清單）。

    
    </div>

12. 可選在 [**輸入已翻譯的數位至測試**] 欄位中輸入值，**然後按一下 [** 執行]。 測試結果會顯示在欄位下方。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未經過測試的語音路線，稍後再重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。

    
    </div>

13. 按一下 [確定]****。

14. 在 [**路由**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立或修改語音路線時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中查看 PSTN 使用狀況記錄](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

