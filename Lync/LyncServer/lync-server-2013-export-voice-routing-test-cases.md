---
title: Lync Server 2013： 匯出語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d014d9c2748a5e6479c0f86ebd32255f3361ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="5ae40-102">匯出語音路由測試案例在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ae40-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ae40-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="5ae40-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5ae40-104">測試案例提供方法讓您在組織中測試語音路由： 您定義要撥打號碼等事項以及要採用的撥號對應表計劃和語音原則和 Lync Server 就可以確認，在這些條件，提供的號碼可以順利進行路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="5ae40-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="5ae40-105">測試案例，可以建立使用 Lync Server Control Panel，通常會儲存只能在其中最初建立及執行這種情況的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5ae40-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="5ae40-106">不過，這些測試案例可以用 XML 檔案 (副檔名為 .vtest) 的形式匯出，然後匯入到其他伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5ae40-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="5ae40-107">如此可讓您在位於拓樸中不同點的不同電腦上執行相同的測試。</span><span class="sxs-lookup"><span data-stu-id="5ae40-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="5ae40-108">若要匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="5ae40-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="5ae40-109">在 Lync Server 控制台中，按一下 [**語音路由**，然後按一下 [**測試語音路由**。</span><span class="sxs-lookup"><span data-stu-id="5ae40-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="5ae40-p102">在 **[測試語音路由]** 索引標籤上，選取要匯出的測試案例。如果要選取多個測試案例，請按一下要匯出的第一個案例，然後按住 Ctrl 鍵，再選取其他要匯出的案例。</span><span class="sxs-lookup"><span data-stu-id="5ae40-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="5ae40-112">依序按一下 **[動作]** 和 **[匯出測試案例]**。</span><span class="sxs-lookup"><span data-stu-id="5ae40-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="5ae40-p103">在 **[另存新檔]** 對話方塊中，選取要儲存匯出的測試案例的資料夾，然後在 **[檔案名稱]** 方塊中輸入產生的 XML 檔案的名稱。請注意，如果您匯出多個測試案例，這些測試案例會全部儲存為單一 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="5ae40-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="5ae40-115">若要儲存測試案例，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5ae40-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ae40-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ae40-116">See Also</span></span>


[<span data-ttu-id="5ae40-117">匯入 Lync Server 2013 中的語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="5ae40-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

