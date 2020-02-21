---
title: Lync Server 2013： 設計互動式語音回應通話流程
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
ms.openlocfilehash: 78032a23fce6bb210ecec6eb828178aabddf9b52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="3a25b-102">Lync Server 2013 中設計互動式語音回應通話流程</span><span class="sxs-lookup"><span data-stu-id="3a25b-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a25b-103">_**上次修改主題：** 2013年-02-25_</span><span class="sxs-lookup"><span data-stu-id="3a25b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3a25b-104">您可以使用互動語音回應 (IVR) 以取得資訊從來電者與適當的佇列將來電導向。</span><span class="sxs-lookup"><span data-stu-id="3a25b-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="3a25b-105">問題和答案配對決定要使用哪一個佇列。</span><span class="sxs-lookup"><span data-stu-id="3a25b-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="3a25b-106">發話者的回應，根據來電者聽到的後續的問題，或路由傳送至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="3a25b-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="3a25b-107">時，IVR 問題和來電者的回應會提供給回應的代理程式人員接受來電提供給代理程式的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="3a25b-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="3a25b-108">IVR 功能概觀</span><span class="sxs-lookup"><span data-stu-id="3a25b-108">Overview of IVR Features</span></span>

<span data-ttu-id="3a25b-109">回應群組應用程式提供語音辨識及文字轉換語音功能 26 語言。</span><span class="sxs-lookup"><span data-stu-id="3a25b-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="3a25b-110">您可以輸入使用文字轉語音] 或 wave (.wav) 或 Windows Media 音訊 (.wma) 檔案時，IVR 問題。</span><span class="sxs-lookup"><span data-stu-id="3a25b-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="3a25b-111">來電者可以使用語音或複頻式訊號 (DTMF) 回應回應。</span><span class="sxs-lookup"><span data-stu-id="3a25b-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="3a25b-112">互動工作流程最多支援兩層的問題，而每個問題最多會有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="3a25b-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="3a25b-113">IVR 詢問來電者的問題，且來電者的回應，根據路由來電者傳送到佇列或詢問的第二個問題。</span><span class="sxs-lookup"><span data-stu-id="3a25b-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="3a25b-114">第二個問題最多也有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="3a25b-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="3a25b-115">根據來電者對第二層問題的答案，可將來電者路由傳送到適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="3a25b-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a25b-116">當您設計通話流程使用 Lync Server 管理命令介面時，您可以定義任何數字的層級的時，IVR 問題和答案的任何數字。</span><span class="sxs-lookup"><span data-stu-id="3a25b-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="3a25b-117">不過，針對來電者可用性，我們建議您使用不超過三個層級的問題，不超過五個解答。</span><span class="sxs-lookup"><span data-stu-id="3a25b-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="3a25b-118">此外，如果您在設計通話流程具有兩個以上的層級的四個以上解答的問題，您無法使用 Lync Server 2013 Control Panel 編輯通話流程。</span><span class="sxs-lookup"><span data-stu-id="3a25b-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="3a25b-119">時，IVR 問題和來電者的回應會提供給回應的代理程式接受來電者。</span><span class="sxs-lookup"><span data-stu-id="3a25b-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="3a25b-120">使用語音技術</span><span class="sxs-lookup"><span data-stu-id="3a25b-120">Working with Speech Technologies</span></span>

<span data-ttu-id="3a25b-121">語音技術，例如語音辨識及文字轉語音]，可提升客戶體驗和更自然地且有效率地讓人員存取資訊。</span><span class="sxs-lookup"><span data-stu-id="3a25b-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="3a25b-122">不過，有時可能的發生其中指定的文字或使用者的語音回應無法識別正確的語音引擎。</span><span class="sxs-lookup"><span data-stu-id="3a25b-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="3a25b-123">例如，"\#」 符號由文字轉換語音引擎轉譯為 word 」 號碼。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="3a25b-124">這個問題，可以藉由下列減輕：</span><span class="sxs-lookup"><span data-stu-id="3a25b-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="3a25b-125">語音引擎可讓來電者五個嘗試回答的問題。</span><span class="sxs-lookup"><span data-stu-id="3a25b-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="3a25b-126">如果來電者不正確地回答的問題 （亦即答案不是其中一個指定的回應） 或未提供所有，來電者取得解答若要回答這個問題的機會。</span><span class="sxs-lookup"><span data-stu-id="3a25b-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="3a25b-127">來電者有五個嘗試回答之前中斷的問題。</span><span class="sxs-lookup"><span data-stu-id="3a25b-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="3a25b-128">您可以設定每個來電者錯誤之後播放自訂的訊息 IVR。</span><span class="sxs-lookup"><span data-stu-id="3a25b-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="3a25b-129">問題重複每次。</span><span class="sxs-lookup"><span data-stu-id="3a25b-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="3a25b-130">若要最小化環境雜訊解譯以回應語音引擎所可能使用較長的回應。</span><span class="sxs-lookup"><span data-stu-id="3a25b-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="3a25b-131">例如，回應應有多個音節，而且應該聲音明顯不同於其他每。</span><span class="sxs-lookup"><span data-stu-id="3a25b-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="3a25b-132">如果您的問題有語音和 DTMF 回應，設定語音回應含有代表概念的文字，而不是 DTMF 回應。</span><span class="sxs-lookup"><span data-stu-id="3a25b-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="3a25b-133">例如，而不是使用 「 按下或說一個 」 使用 「 按 1 或說出帳單。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="3a25b-134">在設計 ivr 時之後，呼叫工作流程、 聆聽提示、 回應給每個使用語音提示，並確認 IVR 聲音]，並如預期的行為。</span><span class="sxs-lookup"><span data-stu-id="3a25b-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="3a25b-135">然後，您可以修改過 ivr 後修正任何解譯問題。</span><span class="sxs-lookup"><span data-stu-id="3a25b-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="3a25b-136">遵循上述範例中，如果您需要參照到\#金鑰]，您可以修正您 IVR 提示字元中使用的索引鍵的名稱，而不是\#符號。</span><span class="sxs-lookup"><span data-stu-id="3a25b-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="3a25b-137">例如，「 按下以講話銷售，請按井字鍵。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="3a25b-138">IVR 設計範例</span><span class="sxs-lookup"><span data-stu-id="3a25b-138">IVR Design Examples</span></span>

<span data-ttu-id="3a25b-139">下列各節包含不同 IVR 案例和問題和答案成對的範例。</span><span class="sxs-lookup"><span data-stu-id="3a25b-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="3a25b-140">具有單層問題的 IVR</span><span class="sxs-lookup"><span data-stu-id="3a25b-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="3a25b-141">下列範例會顯示使用單層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="3a25b-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="3a25b-142">它會使用語音辨識來偵測發話者的回應。</span><span class="sxs-lookup"><span data-stu-id="3a25b-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="3a25b-143">**Question:**「 謝謝您呼叫人力資源。</span><span class="sxs-lookup"><span data-stu-id="3a25b-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="3a25b-144">如果您想要轉接至薪資，說薪資。</span><span class="sxs-lookup"><span data-stu-id="3a25b-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="3a25b-145">否則請說出 HR。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="3a25b-146">**選取選項 1:** 來電者會路由傳送到薪資小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="3a25b-147">**選取選項 2:** 來電者會路由傳送到人力資源小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="3a25b-148">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="3a25b-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="3a25b-149">**單層互動通話流程**</span><span class="sxs-lookup"><span data-stu-id="3a25b-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="3a25b-150">![使用互動語音回應設計通話流程](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "使用互動語音回應設計通話流程")</span><span class="sxs-lookup"><span data-stu-id="3a25b-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="3a25b-151">具有雙層問題的 IVR</span><span class="sxs-lookup"><span data-stu-id="3a25b-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="3a25b-152">下列範例會使用雙層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="3a25b-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="3a25b-153">它可讓來電者使用語音或 DTMF 數字鍵台輸入來回應。</span><span class="sxs-lookup"><span data-stu-id="3a25b-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="3a25b-154">**Question:**「 謝謝您致電 IT Help Desk。</span><span class="sxs-lookup"><span data-stu-id="3a25b-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="3a25b-155">如果您有一個網路存取的問題，請按 1 或說出網路。</span><span class="sxs-lookup"><span data-stu-id="3a25b-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="3a25b-156">如果您有軟體發生問題，請按 2 或說出軟體。</span><span class="sxs-lookup"><span data-stu-id="3a25b-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="3a25b-157">如果您有硬體問題，請按 3 或說出硬體。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="3a25b-158">**選取選項 1:** 來電者會路由傳送到網路支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="3a25b-159">**選取選項 2:** 被詢問來電者後續問題：</span><span class="sxs-lookup"><span data-stu-id="3a25b-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3a25b-160">**Question:**「 若這是作業系統問題，請按 1 或說作業系統的系統。</span><span class="sxs-lookup"><span data-stu-id="3a25b-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="3a25b-161">如果這是內部應用程式有問題，請按 2 或說內部應用程式。</span><span class="sxs-lookup"><span data-stu-id="3a25b-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="3a25b-162">否則，請按 3 或說出其他。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="3a25b-163">**選取選項 1:** 來電者會路由傳送到作業系統支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="3a25b-164">**選取選項 2:** 來電者會路由傳送到內部應用程式支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="3a25b-165">**選取選項 3:** 來電者會路由傳送到軟體支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="3a25b-166">**選取選項 3:** 被詢問來電者後續問題：</span><span class="sxs-lookup"><span data-stu-id="3a25b-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3a25b-167">**Question:**「 若這是印表機問題按 1。</span><span class="sxs-lookup"><span data-stu-id="3a25b-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="3a25b-168">否則，請按 2。 」</span><span class="sxs-lookup"><span data-stu-id="3a25b-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="3a25b-169">**選取選項 1:** 來電者會路由傳送到印表機支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="3a25b-170">**選取選項 2:** 來電者會路由傳送到硬體支援小組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="3a25b-171">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="3a25b-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="3a25b-172">**雙層互動通話流程**</span><span class="sxs-lookup"><span data-stu-id="3a25b-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="3a25b-173">![使用互動語音回應設計通話流程](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "使用互動語音回應設計通話流程")</span><span class="sxs-lookup"><span data-stu-id="3a25b-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="3a25b-174">最佳做法</span><span class="sxs-lookup"><span data-stu-id="3a25b-174">Best Practices</span></span>

<span data-ttu-id="3a25b-175">下列清單描述設計 ivr 時的一些最佳作法：</span><span class="sxs-lookup"><span data-stu-id="3a25b-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="3a25b-176">可讓來電者快速進行工作。</span><span class="sxs-lookup"><span data-stu-id="3a25b-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="3a25b-177">避免提供太多資訊] 或 [在您 IVR 冗長的行銷郵件。</span><span class="sxs-lookup"><span data-stu-id="3a25b-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="3a25b-178">如果您想要包含冗長的郵件，請考慮將它附加至第一個問題而不是歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="3a25b-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="3a25b-179">如果它屬於第一個問題回答問題，但他們無法略過的歡迎訊息，來電者可以略過郵件。</span><span class="sxs-lookup"><span data-stu-id="3a25b-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="3a25b-180">說話發話者的語言。</span><span class="sxs-lookup"><span data-stu-id="3a25b-180">Speak in the caller’s language.</span></span> <span data-ttu-id="3a25b-181">避免 stilted 的語言。</span><span class="sxs-lookup"><span data-stu-id="3a25b-181">Avoid stilted language.</span></span> <span data-ttu-id="3a25b-182">自然地使用。</span><span class="sxs-lookup"><span data-stu-id="3a25b-182">Speak naturally.</span></span>

  - <span data-ttu-id="3a25b-183">寫入最快速且有效的提示。</span><span class="sxs-lookup"><span data-stu-id="3a25b-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="3a25b-184">移除不必要的任何選項。</span><span class="sxs-lookup"><span data-stu-id="3a25b-184">Remove any unnecessary options.</span></span> <span data-ttu-id="3a25b-185">結構資訊，讓來電者的預期回應是句子的結尾。</span><span class="sxs-lookup"><span data-stu-id="3a25b-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="3a25b-186">例如，「 轉接至業務小組，請按 1 」。</span><span class="sxs-lookup"><span data-stu-id="3a25b-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="3a25b-187">使語音回應使用者易記。</span><span class="sxs-lookup"><span data-stu-id="3a25b-187">Make voice responses user friendly.</span></span> <span data-ttu-id="3a25b-188">例如，如果您指定 DTMF 和語音回應，使用類似下面的內容: 「 以轉接至業務小組，請按 1 或說出銷售 」。</span><span class="sxs-lookup"><span data-stu-id="3a25b-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="3a25b-189">整個組織部署之前，請測試過 ivr 後的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="3a25b-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

