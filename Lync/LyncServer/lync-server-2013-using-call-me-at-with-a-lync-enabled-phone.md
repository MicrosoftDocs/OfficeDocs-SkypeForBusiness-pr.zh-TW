---
title: Lync Server 2013： 使用呼叫我在與已啟用 Lync 的電話
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
ms.openlocfilehash: c94820ea7f72b0a2a7afc60b6736c02d96695ea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="3f27f-102">呼叫我在使用已啟用 Lync 的電話與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f27f-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f27f-103">_**上次修改主題：** 2013年-08-09_</span><span class="sxs-lookup"><span data-stu-id="3f27f-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="3f27f-104">Lync 的呼叫我在功能可讓使用者透過行動電話、 「 園地行 」 或其他裝置已連線至公用交換電話網路 (PSTN) 加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="3f27f-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3f27f-105">當您嘗試使用 Lync 加入會議時，您通常會出現與 [**加入會議音訊**] 對話方塊：</span><span class="sxs-lookup"><span data-stu-id="3f27f-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="3f27f-106">![使用 Lync 加入會議音訊] 視窗的螢幕擷取畫面](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入會議音訊] 視窗的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="3f27f-107">如果您選取 [**打電話給我**]，您可以然後選擇下拉式清單中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3f27f-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="3f27f-108">Lync Server 2013 將撥打的電話所選取的號碼，以及您可以再使用該電話來參與會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="3f27f-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="3f27f-109">在下拉式清單會填入您在 [ **Lync-選項**] 對話方塊的 [**電話**] 索引標籤輸入電話號碼 （例如手機、 住家電話或其他電話）：</span><span class="sxs-lookup"><span data-stu-id="3f27f-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="3f27f-110">![Lync 電話設定選項的螢幕擷取畫面](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 電話設定選項的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="3f27f-111">如果您沒有在 [**電話**] 索引標籤上輸入任何電話號碼然後您必須提供的任何數字] 下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="3f27f-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="3f27f-112">不過，您可以一律按一下**新的數字**，並有 Lync Server 撥出您想任何電話號碼：</span><span class="sxs-lookup"><span data-stu-id="3f27f-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="3f27f-113">![Lync 加入會議音訊撥打本人視窗的螢幕擷取畫面](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入會議音訊撥打本人視窗的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="3f27f-114">呼叫我在功能的運作非常好提供其使用其預定的方式： 察覺 Lync Server 通話 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3f27f-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="3f27f-115">不過，您可以執行較不超過最佳的體驗到如果您要求在 Lync 啟用的結束點 （例如，在會議室電話） 呼叫您的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="3f27f-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="3f27f-116">以下是您可能會遇到，以及兩種方式可解決問題的問題。</span><span class="sxs-lookup"><span data-stu-id="3f27f-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="3f27f-117">若要開始，以下是電話的當呼叫我在功能提供 Lync 啟用的電話號碼時，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="3f27f-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="3f27f-118">假設 Ken Myer 會嘗試藉由呼叫他處 1-206-555-1219，已啟用 Lync Server 的電話號碼的 Lync Server 加入會議。</span><span class="sxs-lookup"><span data-stu-id="3f27f-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="3f27f-119">Ken 最初會連線至會議，但之後幾秒鐘 Lync 會顯示訊息，**呼叫未完成，或已經結束**，並 Ken 會顯示已斷線從會議：</span><span class="sxs-lookup"><span data-stu-id="3f27f-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="3f27f-120">![Lync 的螢幕擷取畫面呼叫會議視窗](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 的螢幕擷取畫面呼叫會議視窗")</span><span class="sxs-lookup"><span data-stu-id="3f27f-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="3f27f-121">不過，請注意，已在 Lync 交談視窗內不一致的情形。</span><span class="sxs-lookup"><span data-stu-id="3f27f-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="3f27f-122">Ken Myer 已列於 [**參與者**] 標題下方的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="3f27f-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="3f27f-123">不過，如果您看] 視窗的標題列中，您會看到會議包含 4 參與者總數。</span><span class="sxs-lookup"><span data-stu-id="3f27f-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="3f27f-124">同樣地，如果您在任何其他會議參與者的 [交談] 視窗中查詢您將不會看到 Ken Myer 列出無所不在：</span><span class="sxs-lookup"><span data-stu-id="3f27f-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="3f27f-125">![Lync 參與者清單視窗螢幕擷取畫面](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 參與者清單視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="3f27f-126">尚未，在此同時，Ken myer 的使用者將能夠使用其 Lync 啟用的電話參與通話的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="3f27f-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="3f27f-127">呼叫我在功能實際上具有正常運作，但小於最佳使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="3f27f-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="3f27f-128">有，至少有兩種方式可解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="3f27f-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="3f27f-129">如果您已經有這種方式 （例如 Ken Myer 並未） 加入會議，您通常可以從事不同的形式來解決問題。</span><span class="sxs-lookup"><span data-stu-id="3f27f-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="3f27f-130">例如，如果您要傳送立即訊息 [交談] 視窗會現在會顯示所有會議參與者，包括您自己：</span><span class="sxs-lookup"><span data-stu-id="3f27f-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="3f27f-131">![Lync 交談和參與者清單的螢幕擷取畫面](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 交談和參與者清單的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="3f27f-132">此時您應該能夠參與會議預期的方式。</span><span class="sxs-lookup"><span data-stu-id="3f27f-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="3f27f-133">或者，您可以藉由變更加入會議的方式完全避免此問題。</span><span class="sxs-lookup"><span data-stu-id="3f27f-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="3f27f-134">如果您需要呼叫已啟用 Lync Server 的電話的 Lync Server，您應該稍後加入會議而不需音訊連線。</span><span class="sxs-lookup"><span data-stu-id="3f27f-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="3f27f-135">若要這麼做，請選取 [不加入音訊時出現 [加入會議音訊] 對話方塊：</span><span class="sxs-lookup"><span data-stu-id="3f27f-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="3f27f-136">![Lync 不要加入會議音訊] 視窗的螢幕擷取畫面](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不要加入會議音訊] 視窗的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="3f27f-137">您已經成功連線至會議之後，您可以現在 「 邀請 」 來加入會議也已啟用 Lync Server 的電話。</span><span class="sxs-lookup"><span data-stu-id="3f27f-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="3f27f-138">若要這麼做，將滑鼠放在 [人員] 圖示，然後按一下 [**邀請其他人**：</span><span class="sxs-lookup"><span data-stu-id="3f27f-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="3f27f-139">![Lync 邀請詳細參與者視窗螢幕擷取畫面](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀請詳細參與者視窗螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="3f27f-140">將會帶出 [**傳送 IM** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3f27f-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="3f27f-141">略過對話方塊的標題 （您實際上並不正在傳送立即訊息），並輸入 Lync 啟用的電話的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="3f27f-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="3f27f-142">![傳送 IM] 對話方塊方塊螢幕擷取畫面](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "傳送 IM] 對話方塊方塊螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f27f-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="3f27f-143">按一下 [**確定]** 後，Lync 伺服器就會呼叫在對話方塊中輸入的數字。</span><span class="sxs-lookup"><span data-stu-id="3f27f-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="3f27f-144">連線時，您必須透過 Lync 啟用的電話，完整音訊功能，您將能夠看到並與其互動完整的會議名冊。</span><span class="sxs-lookup"><span data-stu-id="3f27f-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

