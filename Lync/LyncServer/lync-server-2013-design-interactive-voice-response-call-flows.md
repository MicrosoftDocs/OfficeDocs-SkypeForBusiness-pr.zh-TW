---
title: Lync Server 2013：設計互動語音回應通話流程
description: Lync Server 2013：設計互動語音回應通話流程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccf80c1e3226052d952697a4d9fb967f3b681c95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555309"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="91890-103">在 Lync Server 2013 中設計互動語音回應通話流程</span><span class="sxs-lookup"><span data-stu-id="91890-103">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91890-104">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="91890-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="91890-105">您可以使用互動語音回應 (IVR) 從來電者取得資訊，並將來電導向至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="91890-105">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="91890-106">問題和答案配對決定要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="91890-106">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="91890-107">視來電者的回應而定，來電者可能會聽到後續問題，或會路由傳送至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="91890-107">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="91890-108">IVR 問題及來電者的回應會提供給回應的代理人，以接受通話，並將有價值的資訊提供給代理商。</span><span class="sxs-lookup"><span data-stu-id="91890-108">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="91890-109">IVR 功能的概覽</span><span class="sxs-lookup"><span data-stu-id="91890-109">Overview of IVR Features</span></span>

<span data-ttu-id="91890-110">回應群組應用程式可提供26種語言的語音辨識及文字到語音功能。</span><span class="sxs-lookup"><span data-stu-id="91890-110">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="91890-111">您可以使用文字語音轉換或 wave ( .wav) 或 Windows Media 音訊 ( wma) 檔案輸入 IVR 問題。</span><span class="sxs-lookup"><span data-stu-id="91890-111">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="91890-112">來電者可以使用語音或雙音訊式訊號 (DTMF) 回應來回應。</span><span class="sxs-lookup"><span data-stu-id="91890-112">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="91890-113">互動工作流程最多支援兩層的問題，而每個問題最多會有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="91890-113">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="91890-114">IVR 會詢問來電者一個問題，視來電者的回應而定，將來電者路由傳送到佇列或提出第二個問題。</span><span class="sxs-lookup"><span data-stu-id="91890-114">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="91890-115">第二個問題最多也有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="91890-115">The second question can also have four possible answers.</span></span> <span data-ttu-id="91890-116">根據來電者對第二層問題的答案，可將來電者路由傳送到適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="91890-116">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91890-117">當您使用 Lync Server 管理命令介面來設計通話流程時，您可以定義任何號碼層級的 IVR 問題和任何數目的答案。</span><span class="sxs-lookup"><span data-stu-id="91890-117">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="91890-118">不過，對於來電者的可用性，我們建議您不要使用三個以上的問題，每個層次都不會有五個以上的答案。</span><span class="sxs-lookup"><span data-stu-id="91890-118">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="91890-119">此外，如果您設計的通話流程中有兩個以上的問題，每個層次都有四個以上的答案，您就無法使用 Lync Server 2013 控制台編輯通話流程。</span><span class="sxs-lookup"><span data-stu-id="91890-119">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="91890-120">IVR 問題及來電者的回應會提供給接受通話的回應代理人。</span><span class="sxs-lookup"><span data-stu-id="91890-120">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="91890-121">使用語音技術</span><span class="sxs-lookup"><span data-stu-id="91890-121">Working with Speech Technologies</span></span>

<span data-ttu-id="91890-122">語音技術（例如語音辨識及文字轉換語音）可以增強客戶體驗，並讓人員更有效率地存取訊號。</span><span class="sxs-lookup"><span data-stu-id="91890-122">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="91890-123">不過，您可能會出現語音引擎未正確辨識指定的文字或使用者語音回應的情況。</span><span class="sxs-lookup"><span data-stu-id="91890-123">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="91890-124">例如，" \# " 符號會由文字到語音引擎轉譯成字 "number"。</span><span class="sxs-lookup"><span data-stu-id="91890-124">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="91890-125">下列情況可緩解此問題：</span><span class="sxs-lookup"><span data-stu-id="91890-125">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="91890-126">語音引擎可讓來電者有五個嘗試接聽問題。</span><span class="sxs-lookup"><span data-stu-id="91890-126">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="91890-127">如果來電者回答問題的方式不正確 (也就是說，答案不是指定的回應之一) 或根本沒有提供答案，來電者會取得另一個回答問題的機會。</span><span class="sxs-lookup"><span data-stu-id="91890-127">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="91890-128">來電者有五個嘗試在中斷連線之前回答問題。</span><span class="sxs-lookup"><span data-stu-id="91890-128">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="91890-129">您可以設定 IVR 在每一位來電者錯誤之後播放自訂郵件。</span><span class="sxs-lookup"><span data-stu-id="91890-129">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="91890-130">每次都會重複提問。</span><span class="sxs-lookup"><span data-stu-id="91890-130">The question is repeated each time.</span></span>

  - <span data-ttu-id="91890-131">若要將透過語音引擎轉譯成回應的環境噪音可能性降至最低，請使用較長的回應。</span><span class="sxs-lookup"><span data-stu-id="91890-131">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="91890-132">例如，回應應該有一個以上的音節，而且應該會有很大的不同。</span><span class="sxs-lookup"><span data-stu-id="91890-132">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="91890-133">如果您的問題同時有語音和 DTMF 回應，請使用代表概念的字詞（而不是 DTMF 回應）來設定語音回應。</span><span class="sxs-lookup"><span data-stu-id="91890-133">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="91890-134">例如，請不要使用 "按或說一個" 使用 "按1或口述帳單。</span><span class="sxs-lookup"><span data-stu-id="91890-134">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="91890-135">在您設計 IVR 後，請致電工作流程、聆聽提示、使用語音回應每個提示，並確認 IVR 的聲音和行為如預期。</span><span class="sxs-lookup"><span data-stu-id="91890-135">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="91890-136">然後，您可以修改 IVR 以修正任何轉譯問題。</span><span class="sxs-lookup"><span data-stu-id="91890-136">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="91890-137">在上述範例中，如果您需要參照該機 \# 碼，您可以重新寫入您的 IVR 提示字元，而不使用此 \# 符號。</span><span class="sxs-lookup"><span data-stu-id="91890-137">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="91890-138">例如，「與銷售人員交談，按井字鍵。」</span><span class="sxs-lookup"><span data-stu-id="91890-138">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="91890-139">IVR 設計範例</span><span class="sxs-lookup"><span data-stu-id="91890-139">IVR Design Examples</span></span>

<span data-ttu-id="91890-140">下列各節包含不同 IVR 案例及問答對的範例。</span><span class="sxs-lookup"><span data-stu-id="91890-140">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="91890-141">IVR 具有一個層級的問題</span><span class="sxs-lookup"><span data-stu-id="91890-141">IVR with One Level of Questions</span></span>

<span data-ttu-id="91890-142">下列範例顯示使用一層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="91890-142">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="91890-143">它會使用語音辨識偵測來電者的回應。</span><span class="sxs-lookup"><span data-stu-id="91890-143">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="91890-144">**問題：** 「感謝您呼叫人力資源。</span><span class="sxs-lookup"><span data-stu-id="91890-144">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="91890-145">如果您想要對工資單講話，請說出工資單。</span><span class="sxs-lookup"><span data-stu-id="91890-145">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="91890-146">否則請說「HR」。</span><span class="sxs-lookup"><span data-stu-id="91890-146">Otherwise, say HR."</span></span>

  - <span data-ttu-id="91890-147">**選取 [選項 1]：** 來電者會路由傳送到工資單小組。</span><span class="sxs-lookup"><span data-stu-id="91890-147">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="91890-148">**選取選項2：** 來電者會路由傳送至人力資源團隊。</span><span class="sxs-lookup"><span data-stu-id="91890-148">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="91890-149">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="91890-149">The following figure shows the call flow.</span></span>

<span data-ttu-id="91890-150">**一層級互動通話流程**</span><span class="sxs-lookup"><span data-stu-id="91890-150">**One-level interactive call flow**</span></span>

<span data-ttu-id="91890-151">![使用互動語音回應設計通話流程](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "使用互動語音回應設計通話流程")</span><span class="sxs-lookup"><span data-stu-id="91890-151">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="91890-152">IVR 有兩個層級的問題</span><span class="sxs-lookup"><span data-stu-id="91890-152">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="91890-153">下列範例顯示使用兩層級問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="91890-153">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="91890-154">它可讓來電者使用語音或 DTMF 小鍵盤輸入進行回應。</span><span class="sxs-lookup"><span data-stu-id="91890-154">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="91890-155">**問題：** 「感謝您呼叫 IT 問訊台。</span><span class="sxs-lookup"><span data-stu-id="91890-155">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="91890-156">如果有網路存取問題，請按1或說網路。</span><span class="sxs-lookup"><span data-stu-id="91890-156">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="91890-157">如果您有軟體問題，請按2或口述軟體。</span><span class="sxs-lookup"><span data-stu-id="91890-157">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="91890-158">如果有硬體問題，請按3或說硬體。」</span><span class="sxs-lookup"><span data-stu-id="91890-158">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="91890-159">**選取 [選項 1]：** 來電者會路由傳送到網路支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-159">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="91890-160">**選取選項2：** 來電者會問您追蹤問題：</span><span class="sxs-lookup"><span data-stu-id="91890-160">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="91890-161">**問題：** 「如果這是作業系統問題，請按1或口述作業系統。</span><span class="sxs-lookup"><span data-stu-id="91890-161">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="91890-162">如果這是內部應用程式的問題，請按2或說出內部應用程式。</span><span class="sxs-lookup"><span data-stu-id="91890-162">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="91890-163">否則，請按3或說其他。」</span><span class="sxs-lookup"><span data-stu-id="91890-163">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="91890-164">**選取 [選項 1]：** 來電者會路由傳送至作業系統支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-164">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="91890-165">**選取選項2：** 來電者會路由傳送到內部應用程式支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-165">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="91890-166">**選取 [選項 3]：** 來電者會路由傳送到軟體支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-166">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="91890-167">**選取 [選項 3]：** 來電者會問您追蹤問題：</span><span class="sxs-lookup"><span data-stu-id="91890-167">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="91890-168">**問題：** 「如果這是印表機問題，請按1。</span><span class="sxs-lookup"><span data-stu-id="91890-168">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="91890-169">否則，請按2。</span><span class="sxs-lookup"><span data-stu-id="91890-169">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="91890-170">**選取 [選項 1]：** 來電者會路由傳送至印表機支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-170">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="91890-171">**選取選項2：** 來電者會路由傳送至硬體支援小組。</span><span class="sxs-lookup"><span data-stu-id="91890-171">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="91890-172">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="91890-172">The following figure shows the call flow.</span></span>

<span data-ttu-id="91890-173">**雙層互動式通話流程**</span><span class="sxs-lookup"><span data-stu-id="91890-173">**Two-level interactive call flow**</span></span>

<span data-ttu-id="91890-174">![使用互動語音回應設計通話流程](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "使用互動語音回應設計通話流程")</span><span class="sxs-lookup"><span data-stu-id="91890-174">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="91890-175">最佳做法</span><span class="sxs-lookup"><span data-stu-id="91890-175">Best Practices</span></span>

<span data-ttu-id="91890-176">下列清單說明設計 IVR 的一些最佳作法：</span><span class="sxs-lookup"><span data-stu-id="91890-176">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="91890-177">讓來電者快速取得工作。</span><span class="sxs-lookup"><span data-stu-id="91890-177">Let the caller get to the task quickly.</span></span> <span data-ttu-id="91890-178">避免在 IVR 中提供太多資訊或冗長的行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="91890-178">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="91890-179">如果您想要包含很長的訊息，請考慮將它附加到第一個問題，而不是加入歡迎使用的郵件。</span><span class="sxs-lookup"><span data-stu-id="91890-179">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="91890-180">如果來電者是接聽問題的第一個問題的一部分，來電者可以略過此訊息，但無法略過歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="91890-180">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="91890-181">以來電者的語言講話。</span><span class="sxs-lookup"><span data-stu-id="91890-181">Speak in the caller’s language.</span></span> <span data-ttu-id="91890-182">避免 stilted 語言。</span><span class="sxs-lookup"><span data-stu-id="91890-182">Avoid stilted language.</span></span> <span data-ttu-id="91890-183">自然講話。</span><span class="sxs-lookup"><span data-stu-id="91890-183">Speak naturally.</span></span>

  - <span data-ttu-id="91890-184">撰寫有效且有效的提示。</span><span class="sxs-lookup"><span data-stu-id="91890-184">Write efficient and effective prompts.</span></span> <span data-ttu-id="91890-185">移除所有不必要的選項。</span><span class="sxs-lookup"><span data-stu-id="91890-185">Remove any unnecessary options.</span></span> <span data-ttu-id="91890-186">構造資訊，使來電者預期的回應位於句子的結尾。</span><span class="sxs-lookup"><span data-stu-id="91890-186">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="91890-187">例如，「對銷售團隊講話，請按1。」</span><span class="sxs-lookup"><span data-stu-id="91890-187">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="91890-188">讓語音回應使用者易記。</span><span class="sxs-lookup"><span data-stu-id="91890-188">Make voice responses user friendly.</span></span> <span data-ttu-id="91890-189">例如，如果您同時指定 DTMF 和語音回應，請使用類似下列的內容：「說到銷售團隊，按1或說 sales」。</span><span class="sxs-lookup"><span data-stu-id="91890-189">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="91890-190">在您的組織中部署使用者之前，請先在使用者群組上測試 IVR。</span><span class="sxs-lookup"><span data-stu-id="91890-190">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

