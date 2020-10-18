---
title: Lync Server 2013：在具有 Lync 功能的電話上使用電話
description: Lync Server 2013：使用具有 Lync 功能的電話來呼叫我。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd7855e45132b133c78230e7f8769bdab897140
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580419"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="91312-103">在具有 Lync 功能的電話和 Lync Server 2013 上使用呼叫我</span><span class="sxs-lookup"><span data-stu-id="91312-103">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91312-104">_**主題上次修改日期：** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="91312-104">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="91312-105">Lync 中的「呼叫我」功能可讓使用者使用手機、「土地線」或其他連線到公用交換電話網路 (PSTN) 的裝置，加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="91312-105">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="91312-106">當您嘗試使用 Lync 加入會議時，您通常會看到 [ **加入會議音訊** ] 對話方塊：</span><span class="sxs-lookup"><span data-stu-id="91312-106">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="91312-107">![使用 Lync 加入會議音訊視窗螢幕擷取畫面](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入會議音訊視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-107">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="91312-108">如果您選取 [ **呼叫我于**]，則可以從下拉式清單中選取一個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="91312-108">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="91312-109">Lync Server 2013 會撥打所選號碼的電話，然後您就可以使用該電話參加會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="91312-109">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="91312-110">在 [ **Lync –選項**] 對話方塊的 [**電話**] 索引標籤上，您已輸入行動電話、住家電話或其他電話) 的電話號碼 (，會填入下拉式清單：</span><span class="sxs-lookup"><span data-stu-id="91312-110">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="91312-111">![Lync 電話設定選項螢幕擷取畫面](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 電話設定選項螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-111">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="91312-112">如果您未在 [ **電話** ] 索引標籤上輸入任何電話號碼，下拉式方塊中將沒有任何可用的號碼。</span><span class="sxs-lookup"><span data-stu-id="91312-112">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="91312-113">不過，您可以隨時按一下 [ **新增號碼** ]，讓 Lync Server 撥出至您想要的任何電話號碼：</span><span class="sxs-lookup"><span data-stu-id="91312-113">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="91312-114">![Lync 加入會議音訊撥號我視窗螢幕擷取畫面](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入會議音訊撥號我視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-114">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="91312-115">「我的呼叫」功能運作非常好，其方式是讓 Lync Server 呼叫 PSTN 電話號碼，以供您使用。</span><span class="sxs-lookup"><span data-stu-id="91312-115">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="91312-116">不過，如果您要求 Lync Server 在 Lync 啟用的端點撥打您的電話，您可以執行到低於最佳的體驗 (例如，在會議室) 中的電話。</span><span class="sxs-lookup"><span data-stu-id="91312-116">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="91312-117">以下是您可能遇到的問題，以及解決問題的兩種方式。</span><span class="sxs-lookup"><span data-stu-id="91312-117">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="91312-118">若要開始，請在您使用啟用 Lync 功能之電話號碼的電話號碼提供時，執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="91312-118">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="91312-119">假設 Ken Myer 嘗試加入會議，讓 Lync Server 呼叫他在1-206-555-1219 （即啟用 Lync 伺服器的電話號碼）。</span><span class="sxs-lookup"><span data-stu-id="91312-119">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="91312-120">Ken 最初會連接到會議，但是在幾秒後，Lync 將會顯示郵件 **呼叫未完成或已結束**，且 Ken 會顯示已從會議中移除：</span><span class="sxs-lookup"><span data-stu-id="91312-120">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="91312-121">![Lync 通話會議視窗的螢幕擷取畫面](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通話會議視窗的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-121">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="91312-122">不過，請注意，Lync 交談視窗中有差異。</span><span class="sxs-lookup"><span data-stu-id="91312-122">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="91312-123">Ken Myer 是在 [ **參與者** ] 標題底下列出的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="91312-123">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="91312-124">不過，如果您在視窗的標題列中查看，您會看到會議總共有4位參與者。</span><span class="sxs-lookup"><span data-stu-id="91312-124">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="91312-125">同樣地，如果您在其他任何會議參與者的 [交談] 視窗中查看，您將不會看到「Ken Myer」列在任何地方：</span><span class="sxs-lookup"><span data-stu-id="91312-125">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="91312-126">![Lync 參與者清單視窗螢幕擷取畫面](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 參與者清單視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-126">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="91312-127">此外，Ken Myer 也可以使用其 Lync 啟用的電話，參與通話的音訊部分中。</span><span class="sxs-lookup"><span data-stu-id="91312-127">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="91312-128">「我的呼叫」功能實際上已正常運作，但使用者經驗低於最佳。</span><span class="sxs-lookup"><span data-stu-id="91312-128">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="91312-129">至少有兩種方法可解決此問題。</span><span class="sxs-lookup"><span data-stu-id="91312-129">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="91312-130">如果您已以這種方式加入會議 (例如 Ken Myer) ，您通常可以使用不同的形式來解決此問題。</span><span class="sxs-lookup"><span data-stu-id="91312-130">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="91312-131">例如，如果您傳送立即訊息，[交談] 視窗現在會顯示所有會議參與者，包括您：</span><span class="sxs-lookup"><span data-stu-id="91312-131">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="91312-132">![Lync 交談和參與者清單螢幕擷取畫面](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 交談和參與者清單螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-132">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="91312-133">此時，您應該能夠以預期的方式參與會議。</span><span class="sxs-lookup"><span data-stu-id="91312-133">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="91312-134">或者，您可以變更加入會議的方式，以完全避免這一問題。</span><span class="sxs-lookup"><span data-stu-id="91312-134">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="91312-135">如果您需要讓 Lync Server 呼叫啟用 Lync 伺服器的電話，您應該先加入沒有音訊連線的會議。</span><span class="sxs-lookup"><span data-stu-id="91312-135">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="91312-136">若要執行此動作，請選取 [加入會議音訊] 對話方塊時，[不要加入音訊] 對話方塊：</span><span class="sxs-lookup"><span data-stu-id="91312-136">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="91312-137">![Lync 不加入會議音訊視窗螢幕擷取畫面](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入會議音訊視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-137">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="91312-138">成功連接至會議之後，您現在可以「邀請」 Lync Server 啟用的電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="91312-138">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="91312-139">若要這麼做，請將滑鼠放在人脈圖示上，然後按一下 [ **邀請其他人**]：</span><span class="sxs-lookup"><span data-stu-id="91312-139">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="91312-140">![Lync 邀請更多參與者視窗螢幕擷取畫面](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀請更多參與者視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-140">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="91312-141">這會顯示 [ **傳送 IM** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="91312-141">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="91312-142">忽略對話方塊標題 (實際上不會傳送立即訊息) 並輸入啟用 Lync 功能的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="91312-142">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="91312-143">![[傳送 IM] 對話方塊的螢幕擷取畫面](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "[傳送 IM] 對話方塊的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="91312-143">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="91312-144">按一下 **[確定]** 後，Lync Server 會呼叫在對話方塊中輸入的號碼。</span><span class="sxs-lookup"><span data-stu-id="91312-144">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="91312-145">進行連線時，您會透過啟用 Lync 功能的電話獲得完整的音訊功能，而且您將能夠看到完整的會議名單並與其互動。</span><span class="sxs-lookup"><span data-stu-id="91312-145">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

