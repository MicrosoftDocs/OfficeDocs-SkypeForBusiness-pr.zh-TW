---
title: Lync Server 2013：修改語音路由
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
ms.openlocfilehash: e04f3a46d283139e745f1430f835222f25d4d912
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="69071-102">在 Lync Server 2013 中修改語音路由</span><span class="sxs-lookup"><span data-stu-id="69071-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69071-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="69071-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="69071-104">本主題說明如何編輯語音路由。</span><span class="sxs-lookup"><span data-stu-id="69071-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="69071-105">若要建立新的路由，請參閱[create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="69071-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="69071-106">修改語音路由</span><span class="sxs-lookup"><span data-stu-id="69071-106">To modify a voice route</span></span>

1.  <span data-ttu-id="69071-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="69071-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="69071-108">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="69071-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="69071-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="69071-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="69071-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="69071-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69071-111">在左導覽列中，按一下 [**語音路由**]，然後按一下 [**路由**]。</span><span class="sxs-lookup"><span data-stu-id="69071-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="69071-112">在 [**路由**] 頁面上，使用下列其中一種方法來修改語音路由：</span><span class="sxs-lookup"><span data-stu-id="69071-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="69071-113">按一下 voice route 名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="69071-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="69071-114">依序按一下 voice route 名稱、[**編輯**] 和 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="69071-114">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="69071-115">按一下您剛建立之語音路由的新複本，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="69071-115">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="69071-116">在 [**編輯語音路由**] 頁面上的 [**名稱**] 欄位中，輸入語音路由的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="69071-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="69071-117"> (選用) 在 [**描述**] 欄位中，輸入語音路由的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="69071-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="69071-118">若要指定您想要此路由容納的模式，您可以使用**Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。</span><span class="sxs-lookup"><span data-stu-id="69071-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="69071-119">若要使用**Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。</span><span class="sxs-lookup"><span data-stu-id="69071-119">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="69071-120">您可以指定兩種類型的模式對應：</span><span class="sxs-lookup"><span data-stu-id="69071-120">You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="69071-121">**您想要允許的數位的開始位數：** 輸入此路由必須滿足的首碼值 (包括前置 + if （如有必要）) 。</span><span class="sxs-lookup"><span data-stu-id="69071-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="69071-122">例如，輸入 **+ 425** ，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="69071-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="69071-123">針對您想要包含在路由中的每個前置詞值，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="69071-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="69071-124">**例外狀況：** 如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [**例外**狀況]。</span><span class="sxs-lookup"><span data-stu-id="69071-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="69071-125">針對您*不*想要此路由容納的相符模式輸入一個或多個值。</span><span class="sxs-lookup"><span data-stu-id="69071-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="69071-126">例如，若要從路由中排除從 + 425237 開始的數位，請在 [**例外日期**] 欄位中輸入 **+ 425237**的值，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="69071-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="69071-127">若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .net Framework 正則運算式，以指定要套用路由之目的地電話號碼的相符模式。</span><span class="sxs-lookup"><span data-stu-id="69071-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="69071-128">如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。</span><span class="sxs-lookup"><span data-stu-id="69071-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="69071-129">如果您不想讓撥出呼叫出現在來電收件者的電話識別碼，請選取 [**抑制來電者識別碼**]。</span><span class="sxs-lookup"><span data-stu-id="69071-129">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="69071-130">如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的**替代來電者識別碼**。</span><span class="sxs-lookup"><span data-stu-id="69071-130">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="69071-131">若要將一或多個公用交換電話網路 (PSTN) 主幹與語音路由產生關聯，請按一下 [**新增**]，然後從清單中選取一個主幹。</span><span class="sxs-lookup"><span data-stu-id="69071-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69071-132">如果您的部署包含任何 Microsoft Office 通訊伺服器 2007 R2 轉送伺服器，這些伺服器也會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="69071-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="69071-133">若要將一或多個 PSTN 使用方式與語音路由產生關聯，請按一下 [**選取**]，然後從為您的企業語音部署定義的 PSTN 使用方式記錄清單中，選擇記錄。</span><span class="sxs-lookup"><span data-stu-id="69071-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69071-134">若要查看每個可用 PSTN 使用方式記錄的屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用方式記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="69071-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="69071-135">若要建立或編輯 PSTN 使用方式記錄，請參閱<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中建立語音原則和設定 pstn 使用方式記錄</A>，或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改語音原則和設定 pstn 使用方式記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="69071-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="69071-p110">排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。</span><span class="sxs-lookup"><span data-stu-id="69071-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69071-138">相對於語音原則，其中列出 PSTN 使用方式記錄的順序很重要，語音路由中的 PSTN 使用方式記錄的順序是無關緊要的。</span><span class="sxs-lookup"><span data-stu-id="69071-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="69071-139">不過，我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="69071-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="69071-140"> (Lync Server 從左上開始遍歷清單。 ) </span><span class="sxs-lookup"><span data-stu-id="69071-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="69071-141"> (選用) 在 [**輸入要測試的轉譯的號碼**] 欄位中輸入值，然後按一下 [**移至**]。</span><span class="sxs-lookup"><span data-stu-id="69071-141">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="69071-142">測試結果會顯示在欄位底下。</span><span class="sxs-lookup"><span data-stu-id="69071-142">The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69071-143">您可以儲存尚未通過測試的語音路由，然後稍後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="69071-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="69071-144">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="69071-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="69071-145">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69071-145">Click **OK**.</span></span>

14. <span data-ttu-id="69071-146">在 [**路由**] 頁面上，按一下 [**認可**]，然後按一下 [**全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="69071-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69071-147">當您建立或修改語音路由時，您必須執行「<STRONG>認可全部</STRONG>」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="69071-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="69071-148">如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。</span><span class="sxs-lookup"><span data-stu-id="69071-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69071-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="69071-149">See Also</span></span>


[<span data-ttu-id="69071-150">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="69071-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="69071-151">在 Lync Server 2013 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="69071-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="69071-152">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="69071-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="69071-153">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="69071-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="69071-154">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="69071-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="69071-155">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="69071-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

