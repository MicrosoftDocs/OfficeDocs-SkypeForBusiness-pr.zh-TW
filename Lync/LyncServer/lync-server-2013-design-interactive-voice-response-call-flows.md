---
title: Lync Server 2013：設計互動語音回應通話流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487fa3d4842ad67f3433966a08a889e454450351
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="c06cb-102">在 Lync Server 2013 中設計互動語音回應系統通話流程</span><span class="sxs-lookup"><span data-stu-id="c06cb-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c06cb-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c06cb-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c06cb-104">您可以使用互動式語音回應（IVR），從來電者取得資訊，並將呼叫定向至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="c06cb-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="c06cb-105">問題與答案配對決定要使用哪個佇列。</span><span class="sxs-lookup"><span data-stu-id="c06cb-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="c06cb-106">視來電者的回應而定，來電者可能會聽到後續問題，或是路由至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="c06cb-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="c06cb-107">IVR 問題與來電者的回應會提供給接受通話的回應代理程式，提供有價值的資訊給代理程式。</span><span class="sxs-lookup"><span data-stu-id="c06cb-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="c06cb-108">IVR 功能概覽</span><span class="sxs-lookup"><span data-stu-id="c06cb-108">Overview of IVR Features</span></span>

<span data-ttu-id="c06cb-109">回應群組應用程式提供的語音辨識和文字轉換語音功能都有26種語言。</span><span class="sxs-lookup"><span data-stu-id="c06cb-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="c06cb-110">您可以使用文字轉換語音或波形（.wav）或 Windows Media 音訊（.wma）檔案輸入 IVR 問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="c06cb-111">呼叫者可以使用語音或雙音調 multifrequency （DTMF）回應來回應。</span><span class="sxs-lookup"><span data-stu-id="c06cb-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="c06cb-112">互動式工作流程最多可支援兩個層級的問題，每個問題都有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="c06cb-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="c06cb-113">IVR 會向呼叫者提出問題，視來電者的回應而定，將呼叫者路由至佇列或提出第二個問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="c06cb-114">第二個問題也可能有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="c06cb-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="c06cb-115">根據第二層問題的答案而定，來電者會路由至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="c06cb-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c06cb-116">當您使用 Lync Server 管理命令介面設計通話流程時，您可以定義任何數位階層的 IVR 問題及任何數目的答案。</span><span class="sxs-lookup"><span data-stu-id="c06cb-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="c06cb-117">不過，對於呼叫者的可用性，我們建議您不要使用超過三層的問題，每一個都不超過五個答案。</span><span class="sxs-lookup"><span data-stu-id="c06cb-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="c06cb-118">此外，如果您設計的通話流程中有兩個以上的問題，每個層次都有四個以上的答案，您就無法使用 Lync Server 2013 [控制台] 來編輯通話流程。</span><span class="sxs-lookup"><span data-stu-id="c06cb-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="c06cb-119">IVR 問題及來電者的回應會提供給接受通話的回應代理程式。</span><span class="sxs-lookup"><span data-stu-id="c06cb-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="c06cb-120">使用語音技術</span><span class="sxs-lookup"><span data-stu-id="c06cb-120">Working with Speech Technologies</span></span>

<span data-ttu-id="c06cb-121">語音技術（例如語音辨識和文字轉換語音）可加強客戶體驗，讓使用者更容易地存取訊號。</span><span class="sxs-lookup"><span data-stu-id="c06cb-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="c06cb-122">不過，您可能會有語音引擎無法正確辨識指定文字或使用者語音回應的情況。</span><span class="sxs-lookup"><span data-stu-id="c06cb-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="c06cb-123">例如，"\#" 符號是由文字到語音引擎所轉譯為「數位」一詞。</span><span class="sxs-lookup"><span data-stu-id="c06cb-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="c06cb-124">您可以透過下列方式緩解此問題：</span><span class="sxs-lookup"><span data-stu-id="c06cb-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="c06cb-125">語音引擎提供給呼叫者五次，回答問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="c06cb-126">如果來電者回答的問題不正確（也就是說，答案不是指定的回應），或是根本無法提供答案，則呼叫者會收到另一個回答問題的機會。</span><span class="sxs-lookup"><span data-stu-id="c06cb-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="c06cb-127">呼叫者有五個嘗試在中斷連線之前回答問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="c06cb-128">您可以將 IVR 設定為在每個本機號碼之後，播放自訂的訊息。</span><span class="sxs-lookup"><span data-stu-id="c06cb-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="c06cb-129">每次都會重複出現這個問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="c06cb-130">若要將由語音引擎轉譯為回應的環境干擾可能性降至最低，請使用較長的回應。</span><span class="sxs-lookup"><span data-stu-id="c06cb-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="c06cb-131">例如，回應應該有一個以上的音節，而且應該會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="c06cb-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="c06cb-132">如果您的問題同時具有語音和 DTMF 回應，請使用代表概念的文字（而不是 DTMF 回應）來設定語音回應。</span><span class="sxs-lookup"><span data-stu-id="c06cb-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="c06cb-133">例如，請不要使用「按下或說一次」，而是按1或說帳單。」</span><span class="sxs-lookup"><span data-stu-id="c06cb-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="c06cb-134">在您設計 IVR 之後，請呼叫工作流程、聆聽提示、使用語音回應每個提示，並確認 IVR 的音效和行為如期運作。</span><span class="sxs-lookup"><span data-stu-id="c06cb-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="c06cb-135">然後，您可以修改 IVR 以修正任何轉譯問題。</span><span class="sxs-lookup"><span data-stu-id="c06cb-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="c06cb-136">在前面的範例中，如果您需要參照該\#索引鍵，可以重新寫入 IVR 提示，以使用索引鍵名稱，而不是\#符號。</span><span class="sxs-lookup"><span data-stu-id="c06cb-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="c06cb-137">例如，若要與銷售額交談，請按井號鍵。</span><span class="sxs-lookup"><span data-stu-id="c06cb-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="c06cb-138">IVR 設計範例</span><span class="sxs-lookup"><span data-stu-id="c06cb-138">IVR Design Examples</span></span>

<span data-ttu-id="c06cb-139">下列各節包含不同 IVR 案例與問題與答案組的範例。</span><span class="sxs-lookup"><span data-stu-id="c06cb-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="c06cb-140">包含一層問題的 IVR</span><span class="sxs-lookup"><span data-stu-id="c06cb-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="c06cb-141">下列範例顯示使用一層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="c06cb-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="c06cb-142">它會使用語音辨識來偵測來電者的回應。</span><span class="sxs-lookup"><span data-stu-id="c06cb-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="c06cb-143">**問題：**「感謝您打電話給人力資源。</span><span class="sxs-lookup"><span data-stu-id="c06cb-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="c06cb-144">如果您想要與工資單通話，請說出工資。</span><span class="sxs-lookup"><span data-stu-id="c06cb-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="c06cb-145">否則請說人力資源。」</span><span class="sxs-lookup"><span data-stu-id="c06cb-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="c06cb-146">**已選取選項1：** 來電者會傳送給工資小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="c06cb-147">**已選取選項2：** 來電者會傳送給人力資源小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="c06cb-148">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="c06cb-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="c06cb-149">**一對一互動式呼叫流程**</span><span class="sxs-lookup"><span data-stu-id="c06cb-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="c06cb-150">使用互動式語音![Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "設計通話流程（使用互動式語音 Respo") ）設計通話流程</span><span class="sxs-lookup"><span data-stu-id="c06cb-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="c06cb-151">IVR 有兩個等級的問題</span><span class="sxs-lookup"><span data-stu-id="c06cb-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="c06cb-152">下列範例顯示的是使用兩層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="c06cb-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="c06cb-153">它可讓呼叫者使用語音或 DTMF 小鍵盤輸入來回應。</span><span class="sxs-lookup"><span data-stu-id="c06cb-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="c06cb-154">**問題：**「感謝您致電 IT 技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="c06cb-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="c06cb-155">如果有網路存取問題，請按1或說 [網路]。</span><span class="sxs-lookup"><span data-stu-id="c06cb-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="c06cb-156">如果您有軟體問題，請按2或說軟體。</span><span class="sxs-lookup"><span data-stu-id="c06cb-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="c06cb-157">如果有硬體問題，請按3或說硬體。」</span><span class="sxs-lookup"><span data-stu-id="c06cb-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="c06cb-158">**已選取選項1：** 來電者會路由至網路支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="c06cb-159">**已選取選項2：** 來電者會問到待處理問題：</span><span class="sxs-lookup"><span data-stu-id="c06cb-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="c06cb-160">**問題：**「如果這是作業系統問題，請按1或說作業系統。</span><span class="sxs-lookup"><span data-stu-id="c06cb-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="c06cb-161">如果這是內部應用程式的問題，請按2或說出內部應用程式。</span><span class="sxs-lookup"><span data-stu-id="c06cb-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="c06cb-162">否則，請按3或說 [其他]。</span><span class="sxs-lookup"><span data-stu-id="c06cb-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="c06cb-163">**已選取選項1：** 來電者會路由至作業系統支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="c06cb-164">**已選取選項2：** 來電者會路由到內部應用程式支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="c06cb-165">**已選取選項3：** 來電者會傳送給軟體支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="c06cb-166">**已選取選項3：** 來電者會問到待處理問題：</span><span class="sxs-lookup"><span data-stu-id="c06cb-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="c06cb-167">**問題：**「如果這是印表機問題，請按1。</span><span class="sxs-lookup"><span data-stu-id="c06cb-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="c06cb-168">否則，請按2。</span><span class="sxs-lookup"><span data-stu-id="c06cb-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="c06cb-169">**已選取選項1：** 來電者會傳送給印表機支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="c06cb-170">**已選取選項2：** 來電者會路由到硬體支援小組。</span><span class="sxs-lookup"><span data-stu-id="c06cb-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="c06cb-171">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="c06cb-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="c06cb-172">**兩層互動式通話流程**</span><span class="sxs-lookup"><span data-stu-id="c06cb-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="c06cb-173">使用互動式語音![Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "設計通話流程（使用互動式語音 Respo") ）設計通話流程</span><span class="sxs-lookup"><span data-stu-id="c06cb-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="c06cb-174">最佳做法</span><span class="sxs-lookup"><span data-stu-id="c06cb-174">Best Practices</span></span>

<span data-ttu-id="c06cb-175">下列清單說明設計 IVR 的一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="c06cb-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="c06cb-176">讓呼叫者快速取得工作。</span><span class="sxs-lookup"><span data-stu-id="c06cb-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="c06cb-177">避免在您的 IVR 中提供太多的資訊或冗長的行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="c06cb-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="c06cb-178">如果您想要包含較長的訊息，請考慮將它附加到第一個問題，而不是加入 [歡迎使用] 訊息。</span><span class="sxs-lookup"><span data-stu-id="c06cb-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="c06cb-179">如果您回答的問題是第一個問題的一部分，來電者可以略過這封郵件，但他們無法略過歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="c06cb-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="c06cb-180">在來電者語言中說話。</span><span class="sxs-lookup"><span data-stu-id="c06cb-180">Speak in the caller’s language.</span></span> <span data-ttu-id="c06cb-181">避免 stilted 語言。</span><span class="sxs-lookup"><span data-stu-id="c06cb-181">Avoid stilted language.</span></span> <span data-ttu-id="c06cb-182">自然說話。</span><span class="sxs-lookup"><span data-stu-id="c06cb-182">Speak naturally.</span></span>

  - <span data-ttu-id="c06cb-183">撰寫高效且有效的提示。</span><span class="sxs-lookup"><span data-stu-id="c06cb-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="c06cb-184">移除任何不必要的選項。</span><span class="sxs-lookup"><span data-stu-id="c06cb-184">Remove any unnecessary options.</span></span> <span data-ttu-id="c06cb-185">構造資訊，讓來電者預期的回應在句子的結尾。</span><span class="sxs-lookup"><span data-stu-id="c06cb-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="c06cb-186">例如，「若要與銷售團隊通話，請按1。」</span><span class="sxs-lookup"><span data-stu-id="c06cb-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="c06cb-187">讓語音回復使用者更容易。</span><span class="sxs-lookup"><span data-stu-id="c06cb-187">Make voice responses user friendly.</span></span> <span data-ttu-id="c06cb-188">例如，如果您指定 DTMF 和語音回應，請使用如下所示的內容：「若要與銷售團隊進行通話，請按1或說出銷售。」</span><span class="sxs-lookup"><span data-stu-id="c06cb-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="c06cb-189">在您的組織中部署使用者群組之前，請先測試一組使用者的 IVR。</span><span class="sxs-lookup"><span data-stu-id="c06cb-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

