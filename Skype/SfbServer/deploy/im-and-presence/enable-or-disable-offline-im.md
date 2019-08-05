---
title: 在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)。
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191533"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="39c54-103">在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)</span><span class="sxs-lookup"><span data-stu-id="39c54-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="39c54-104">瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)。</span><span class="sxs-lookup"><span data-stu-id="39c54-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="39c54-105">在商務用 Skype Server 中啟用離線立即訊息 (IM)</span><span class="sxs-lookup"><span data-stu-id="39c54-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="39c54-106">離線 IM 是內置於商務用 Skype 用戶端 (2016 C2R 組建16.0.6701.1000 或更新版本) 的用戶端功能, 可利用 Exchange Web 服務 (EWS) 從商務用 Skype 用戶端傳送郵件給使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="39c54-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="39c54-107">離線 IM 使用 Exchange Web 服務 (EWS) 從商務用 Skype 用戶端傳送離線郵件至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="39c54-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="39c54-108">您必須提供 EWS, 才能傳送離線訊息給商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="39c54-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="39c54-109">若要深入瞭解如何規劃立即訊息和目前狀態, 請參閱[規劃商務用 Skype Server 中的立即訊息和目前狀態](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="39c54-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="39c54-110">如果使用者的信箱託管于 Exchange 內部部署中, 則需要商務用 Skype 用戶端 (2016 C2R 組建 16.0.6920.1000)</span><span class="sxs-lookup"><span data-stu-id="39c54-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="39c54-111">在商務用 Skype Server 中啟用或停用離線 IM</span><span class="sxs-lookup"><span data-stu-id="39c54-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="39c54-112">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="39c54-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="39c54-113">執行下列命令以啟用離線 IM。</span><span class="sxs-lookup"><span data-stu-id="39c54-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="39c54-114">在商務用 Skype Server 2015 CU3 中, [EnableOfflineIM] 選項預設會設定為 [$True]。</span><span class="sxs-lookup"><span data-stu-id="39c54-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="39c54-115">若要停用, 請將此值設定為 [$False]。</span><span class="sxs-lookup"><span data-stu-id="39c54-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="39c54-116">執行下列命令, 確認已設定儲存離線 IM 的功能。</span><span class="sxs-lookup"><span data-stu-id="39c54-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="39c54-117">與 Exchange 進行離線 IM 整合</span><span class="sxs-lookup"><span data-stu-id="39c54-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="39c54-118">如果寄件者擁有可停用自動將離線訊息儲存至 [交談記錄] 資料夾 (EnableIMAutoArchiving = $false) 的用戶端原則, 就不會提供離線 IM。</span><span class="sxs-lookup"><span data-stu-id="39c54-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="39c54-119">沒有任何機制可以檢查收件者是否可以接收離線訊息。</span><span class="sxs-lookup"><span data-stu-id="39c54-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="39c54-120">如果您在同一個組織中傳送離線訊息, 這些郵件將會以電子郵件訊息的方式收到, 並將郵件分類至 IM。MissedConversation 並將包含在 Outlook 未接的**交談**資料夾中, 以及將在商務用 Skype 用戶端的 [最近的清單/交談記錄] 索引標籤中挑選的交談記錄。</span><span class="sxs-lookup"><span data-stu-id="39c54-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="39c54-121">如果您是從同盟組織傳送的離線郵件, 他們將會以電子郵件訊息 (不含 IM) 的形式收到。MisssedConversation 並不會在 [未接的交談] 或 [交談記錄] 資料夾中拾取。</span><span class="sxs-lookup"><span data-stu-id="39c54-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="39c54-122">疑難排解</span><span class="sxs-lookup"><span data-stu-id="39c54-122">Troubleshooting</span></span>

<span data-ttu-id="39c54-123">當您收到並處理離線訊息時, 會出現兩分鐘的計時器。</span><span class="sxs-lookup"><span data-stu-id="39c54-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="39c54-124">如果離線訊息無法處理, 它們會出現在下列目錄中:</span><span class="sxs-lookup"><span data-stu-id="39c54-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="39c54-125">主要的商務用 Skype ETL 記錄將包含離線訊息處理的相關資訊, 也是您要調查/疑難排解的最佳來源。</span><span class="sxs-lookup"><span data-stu-id="39c54-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="39c54-126">已報告離線訊息無法傳送的問題, 且 [草稿] 資料夾已填入郵件中。</span><span class="sxs-lookup"><span data-stu-id="39c54-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="39c54-127">此發生于 Exchange 內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="39c54-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="39c54-128">此問題已于6/14/2016 的所有 C2R 通道中修正。</span><span class="sxs-lookup"><span data-stu-id="39c54-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
