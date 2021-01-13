---
title: '在商務用 Skype Server 中啟用或停用離線立即訊息 (IM) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM) 。
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801943"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="5274f-103">在商務用 Skype Server 中啟用或停用離線立即訊息 (IM) </span><span class="sxs-lookup"><span data-stu-id="5274f-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="5274f-104">瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM) 。</span><span class="sxs-lookup"><span data-stu-id="5274f-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="5274f-105">啟用商務用 Skype Server 中的離線立即訊息 (IM) </span><span class="sxs-lookup"><span data-stu-id="5274f-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="5274f-106">離線 IM 是內置於商務用 Skype 用戶端的用戶端功能 (2016 C2R build 16.0.6701.1000 或以上) 利用 Exchange Web 服務 (EWS) ，將郵件從商務用 Skype 用戶端傳送至使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="5274f-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="5274f-107">離線 IM 使用 Exchange Web 服務 (EWS) 以從商務用 Skype 用戶端將離線郵件傳送至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="5274f-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="5274f-108">EWS 必須可供商務用 Skype 用戶端使用，以供傳送離線訊息使用。</span><span class="sxs-lookup"><span data-stu-id="5274f-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="5274f-109">若要深入瞭解規劃立即訊息和目前狀態，請參閱 [在商務用 Skype Server 中規劃立即訊息和目前狀態](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="5274f-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5274f-110">如果使用者的信箱主控于 Exchange On-Premises 中，商務用 Skype 用戶端 (2016 C2R 組建 16.0.6920.1000) 是必要的</span><span class="sxs-lookup"><span data-stu-id="5274f-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="5274f-111">啟用或停用商務用 Skype Server 中的離線 IM</span><span class="sxs-lookup"><span data-stu-id="5274f-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="5274f-112">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5274f-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5274f-113">執行下列命令以啟用離線 IM。</span><span class="sxs-lookup"><span data-stu-id="5274f-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="5274f-114">在商務用 Skype Server 2015 CU3 中，EnableOfflineIM 選項預設設定為 $True。</span><span class="sxs-lookup"><span data-stu-id="5274f-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="5274f-115">若要停用，請將此值設為 $False。</span><span class="sxs-lookup"><span data-stu-id="5274f-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="5274f-116">執行下列命令，以確認已設定儲存離線 IM 的功能。</span><span class="sxs-lookup"><span data-stu-id="5274f-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="5274f-117">與 Exchange 的離線 IM 整合</span><span class="sxs-lookup"><span data-stu-id="5274f-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="5274f-118">如果寄件者的用戶端原則停用自動儲存至 [交談記錄] 資料夾中的離線郵件，則不能使用離線 IM (EnableIMAutoArchiving = $false) 。</span><span class="sxs-lookup"><span data-stu-id="5274f-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="5274f-119">沒有任何機制可檢查收件者是否可以接收離線郵件。</span><span class="sxs-lookup"><span data-stu-id="5274f-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="5274f-120">針對相同組織內傳送的離線郵件，它們會以 IM 郵件類別的電子郵件訊息的形式接收。 MissedConversation 並將包含在 Outlook 未 **交談** 資料夾中，以及將在商務用 Skype 用戶端的 [最近的清單/交談記錄] 索引標籤中選取的交談記錄。</span><span class="sxs-lookup"><span data-stu-id="5274f-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="5274f-121">對於從同盟組織傳送的離線郵件，他們會以電子郵件訊息方式接收，但不會收到 MisssedConversation，也不會在未接的交談或交談記錄資料夾中領取。</span><span class="sxs-lookup"><span data-stu-id="5274f-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="5274f-122">疑難排解</span><span class="sxs-lookup"><span data-stu-id="5274f-122">Troubleshooting</span></span>

<span data-ttu-id="5274f-123">當離線郵件接收及處理時，會有兩分鐘的計時器。</span><span class="sxs-lookup"><span data-stu-id="5274f-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="5274f-124">如果離線訊息無法處理，它們就會出現在下列目錄中：</span><span class="sxs-lookup"><span data-stu-id="5274f-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="5274f-125">主要商務用 Skype ETL 記錄會包含離線郵件處理的相關資訊，也是您要調查/疑難排解的最佳來源。</span><span class="sxs-lookup"><span data-stu-id="5274f-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5274f-126">已報告「離線訊息傳送失敗」和「草稿」資料夾填滿郵件的問題。</span><span class="sxs-lookup"><span data-stu-id="5274f-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="5274f-127">Exchange On-Premises 信箱發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="5274f-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="5274f-128">從6/14/2016 起，所有 C2R 通道都已修復此問題。</span><span class="sxs-lookup"><span data-stu-id="5274f-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
