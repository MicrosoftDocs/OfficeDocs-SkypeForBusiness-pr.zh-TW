---
title: 應答自動回應及呼叫佇列通話
ms.reviewer: waseemh
author: SerdarSoysal
ms.author: serdars
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ea09e005dea2a89cb23b55a8ac59eaf491df460
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582820"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="8b833-103">直接從 Teams 回答自動語音應答和通話佇列的通話</span><span class="sxs-lookup"><span data-stu-id="8b833-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="8b833-104">團隊使用者可以從雲端自動語音應答並直接從其小組用戶端呼叫佇列來接收和接聽通話。</span><span class="sxs-lookup"><span data-stu-id="8b833-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="8b833-105">什麼是自動語音應答及呼叫佇列？</span><span class="sxs-lookup"><span data-stu-id="8b833-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="8b833-106">雲端自動語音應答提供一系列的語音提示或音訊檔案，當來電者撥入組織時，會聽到該語音提示，而不是人工操作員。</span><span class="sxs-lookup"><span data-stu-id="8b833-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="8b833-107">自動接聽：讓呼叫者在功能表系統中移動、撥打電話，或使用電話鍵台 (DTMF) 或使用語音辨識的語音輸入來找出使用者。</span><span class="sxs-lookup"><span data-stu-id="8b833-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="8b833-108">雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及搜尋下一個可用的呼叫代理程式，以處理通話，而呼叫者正在聆聽音樂的人員。</span><span class="sxs-lookup"><span data-stu-id="8b833-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="8b833-109">您可以為組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="8b833-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="8b833-110">處理自動語音應答或通話佇列通話</span><span class="sxs-lookup"><span data-stu-id="8b833-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="8b833-111">使用者將能夠在來電前，在自動語音應答或通話佇列中區別來電。</span><span class="sxs-lookup"><span data-stu-id="8b833-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="8b833-112">隨著來電者的名稱和/或數位，每次呼叫都會包含來電者嘗試到達者的資訊，為使用者提供更好的方式來解決來電者。</span><span class="sxs-lookup"><span data-stu-id="8b833-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="8b833-113">下圖顯示如何將來自自動語音應答或通話佇列的本機號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="8b833-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![來電通知的螢幕擷取畫面](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="8b833-115">當您接聽自動語音應答或通話佇列呼叫之後，使用者就可以像處理任何其他通話一樣處理呼叫，&#x2014; 他們可以在其他使用者中新增或會議，或將來電轉接至另一方。</span><span class="sxs-lookup"><span data-stu-id="8b833-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="8b833-116">此外，自動來電呼叫將根據使用者的設定來轉寄。</span><span class="sxs-lookup"><span data-stu-id="8b833-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="8b833-117">通話佇列通話不會根據使用者的設定來轉寄。</span><span class="sxs-lookup"><span data-stu-id="8b833-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="8b833-118">這是為了確保呼叫者保留在佇列中，直到工程師可以接聽通話且來電者不會被意外轉寄。</span><span class="sxs-lookup"><span data-stu-id="8b833-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="8b833-119">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="8b833-119">Supported clients</span></span>

<span data-ttu-id="8b833-120">在下列用戶端提供自動語音應答及呼叫佇列呼叫支援：</span><span class="sxs-lookup"><span data-stu-id="8b833-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="8b833-121">Microsoft 團隊 Windows 用戶端 (32 和64位版本) </span><span class="sxs-lookup"><span data-stu-id="8b833-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="8b833-122">Microsoft 團隊 Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="8b833-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="8b833-123">Microsoft 團隊 iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="8b833-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="8b833-124">Microsoft 團隊 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="8b833-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="8b833-125">針對 Microsoft 團隊設定自動語音應答及呼叫佇列支援</span><span class="sxs-lookup"><span data-stu-id="8b833-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="8b833-126">若要在 Microsoft 團隊中接收自動語音應答及呼叫佇列通話，您必須設定您的互通性原則和升級原則。</span><span class="sxs-lookup"><span data-stu-id="8b833-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="8b833-127">請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="8b833-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="8b833-128">如果您沒有設定自動語音應答及/或通話佇列，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答及[建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="8b833-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b833-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="8b833-129">Related topics</span></span>

-    [<span data-ttu-id="8b833-130">什麼是 Microsoft 365 或 Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="8b833-130">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="8b833-131">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="8b833-131">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="8b833-132">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="8b833-132">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="8b833-133">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="8b833-133">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

