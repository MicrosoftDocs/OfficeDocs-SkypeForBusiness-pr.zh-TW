---
title: 直接從 Teams 回答自動語音應答和通話佇列的通話
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 描述雲端自動語音應答和通話佇列，並說明您可以如何在團隊中回答這些通話。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e864e32409730373d98263215b0bcc35d9b404d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825311"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="9f2be-103">直接從 Teams 回答自動語音應答和通話佇列的通話</span><span class="sxs-lookup"><span data-stu-id="9f2be-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="9f2be-104">團隊使用者可以從雲端自動語音應答並直接從其小組用戶端呼叫佇列來接收和接聽通話。</span><span class="sxs-lookup"><span data-stu-id="9f2be-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="9f2be-105">針對團隊使用者，現在可以使用自動語音應答功能，而且通話佇列功能是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="9f2be-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="9f2be-106">什麼是自動語音應答及呼叫佇列？</span><span class="sxs-lookup"><span data-stu-id="9f2be-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="9f2be-107">雲端自動語音應答提供一系列的語音提示或音訊檔案，當來電者撥入組織時，會聽到該語音提示，而不是人工操作員。</span><span class="sxs-lookup"><span data-stu-id="9f2be-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="9f2be-108">自動接聽：可讓呼叫者透過功能表系統、撥打電話或使用語音辨識來尋找使用者（使用電話鍵台（DTMF）或語音輸入。</span><span class="sxs-lookup"><span data-stu-id="9f2be-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="9f2be-109">雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。</span><span class="sxs-lookup"><span data-stu-id="9f2be-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="9f2be-110">您可以為組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="9f2be-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="9f2be-111">處理自動語音應答或通話佇列通話</span><span class="sxs-lookup"><span data-stu-id="9f2be-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="9f2be-112">使用者將能夠在來電前，在自動語音應答或通話佇列中區別來電。</span><span class="sxs-lookup"><span data-stu-id="9f2be-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="9f2be-113">隨著來電者的名稱和/或數位，每次呼叫都會包含來電者嘗試到達者的資訊，為使用者提供更好的方式來解決來電者。</span><span class="sxs-lookup"><span data-stu-id="9f2be-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="9f2be-114">下圖顯示如何將來自自動語音應答或通話佇列的本機號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="9f2be-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![來電通知的螢幕擷取畫面](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="9f2be-116">當您接聽自動語音應答或通話佇列呼叫之後，使用者就可以像處理任何其他通話一樣處理呼叫，&#x2014; 他們可以在其他使用者中新增或會議，或將來電轉接至另一方。</span><span class="sxs-lookup"><span data-stu-id="9f2be-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="9f2be-117">此外，自動來電呼叫將根據使用者的設定來轉寄。</span><span class="sxs-lookup"><span data-stu-id="9f2be-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="9f2be-118">通話佇列通話不會根據使用者的設定來轉寄。</span><span class="sxs-lookup"><span data-stu-id="9f2be-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="9f2be-119">這是為了確保呼叫者保留在佇列中，直到工程師可以接聽通話且來電者不會被意外轉寄。</span><span class="sxs-lookup"><span data-stu-id="9f2be-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="9f2be-120">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="9f2be-120">Supported clients</span></span>

<span data-ttu-id="9f2be-121">在下列用戶端提供自動語音應答及呼叫佇列呼叫支援：</span><span class="sxs-lookup"><span data-stu-id="9f2be-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="9f2be-122">Microsoft 團隊 Windows 用戶端（32和64位版本）</span><span class="sxs-lookup"><span data-stu-id="9f2be-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="9f2be-123">Microsoft 團隊 Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="9f2be-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="9f2be-124">Microsoft 團隊 iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="9f2be-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="9f2be-125">Microsoft 團隊 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="9f2be-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="9f2be-126">針對 Microsoft 團隊設定自動語音應答及呼叫佇列支援</span><span class="sxs-lookup"><span data-stu-id="9f2be-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="9f2be-127">若要在 Microsoft 團隊中接收自動語音應答及呼叫佇列通話，您必須設定您的互通性原則和升級原則。</span><span class="sxs-lookup"><span data-stu-id="9f2be-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="9f2be-128">請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="9f2be-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="9f2be-129">如果您沒有設定自動語音應答及/或通話佇列，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答及[建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="9f2be-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f2be-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f2be-130">Related topics</span></span>

-   [<span data-ttu-id="9f2be-131">什麼是 Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="9f2be-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="9f2be-132">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="9f2be-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="9f2be-133">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="9f2be-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="9f2be-134">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="9f2be-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

