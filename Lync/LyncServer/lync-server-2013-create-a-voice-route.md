---
title: Lync Server 2013：建立語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f62b6ba64456b8e892c94117750bf1bc209bc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中建立語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

下列程式說明如何使用 Lync Server 2013 控制台來建立新的語音路由。 若要編輯現有的路由，請參閱[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)以取得此程式。

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>使用 Lync Server 控制台建立語音路由

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**。

4.  按一下 **[路由]**。

5.  按一下 [**新增**] 顯示 [**新增語音路由**] 對話方塊。

6.  在 [**名稱**] 中，輸入語音路由的描述性名稱。

7.   (選用) 在 [**描述**] 中，輸入語音路由的其他描述性資訊。

8.  若要指定您想要此路由容納的模式，您可以使用**Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。
    
      - 若要使用**Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。 您可以指定兩種類型的模式對應：
        
          - **您想要允許的數位的開始位數：** 輸入此路由必須滿足的首碼值 (包括前置 + if （如有必要）) 。 例如，輸入 **+ 425**，然後按一下 [**新增**]。 針對您想要包含在路由中的每個前置詞值，重複此步驟。
        
          - **例外狀況：** 如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [**例外**狀況]。 針對您*不*想要此路由容納的相符模式輸入一個或多個值。 例如，若要從路由中排除從 + 425237 開始的數位，請在 [**例外日期**] 欄位中輸入 **+ 425237**的值，然後按一下 **[確定]**。
    
      - 若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .net Framework 正則運算式，以指定要套用路由之目的地電話號碼的相符模式。 如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。

9.  如果您不想讓撥出電話的電話號碼對來電收件者顯示，請選取 [**抑制來電者識別碼**]。 如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的**替代來電者識別碼**。

10. 若要將一或多個主幹與語音路由產生關聯，請按一下 [**新增**]，然後從清單中選取一個主幹。
    
    <div>
    

    > [!NOTE]  
    > 如果您的部署包含任何 Microsoft Office 通訊伺服器 2007 R2 轉送伺服器，這些伺服器也會出現在清單中。

    
    </div>

11. 若要將一或多個公用交換電話網路 (PSTN) 使用方式與語音路由產生關聯，請按一下 [**選取**]，然後從為您的 Enterprise voice 部署定義的 PSTN 使用方式記錄清單中，選擇記錄。
    
    <div>
    

    > [!NOTE]  
    > 若要查看每個可用 PSTN 使用方式記錄的屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用方式記錄</A>。<BR>若要建立或編輯 PSTN 使用方式記錄，請參閱<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中建立語音原則和設定 pstn 使用方式記錄</A>，或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改語音原則和設定 pstn 使用方式記錄</A>。

    
    </div>

12. 排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。
    
    <div>
    

    > [!NOTE]  
    > 與語音原則不同的是，列出 PSTN 使用方式記錄的順序很重要，因此語音路由中列出 PSTN 使用方式記錄的順序是沒有意義的。 不過，我們建議您依使用頻率來組織清單。 例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (Lync Server 從左上開始遍歷清單。 ) 

    
    </div>

13.  (選用) 在 [**輸入要測試的轉譯的號碼**] 欄位中輸入值，然後按一下 [**移至**]。 測試結果會顯示在欄位底下。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未通過測試的語音路由，然後稍後再加以重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。

    
    </div>

14. 按一下 **[確定]** 以儲存語音路由。

<div>


> [!IMPORTANT]  
> 每當您建立語音路由時，都必須執行「<STRONG>認可全部</STRONG>」命令來發佈設定變更。 如需詳細資訊，請參閱<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中查看 PSTN 使用方式記錄](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

