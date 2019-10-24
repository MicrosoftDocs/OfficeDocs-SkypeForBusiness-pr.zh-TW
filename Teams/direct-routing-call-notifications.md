---
title: 電話系統直向路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37639219"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="6788f-103">管理來電通知</span><span class="sxs-lookup"><span data-stu-id="6788f-103">Manage call notifications</span></span>

<span data-ttu-id="6788f-104">本文說明如何管理使用者的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="6788f-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="6788f-105">您可以將呼叫端點設定為兩個小組，以及協力廠商的專用分支 Exchange （PBX）或會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="6788f-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="6788f-106">例如，如果您想要同時將呼叫傳送給使用者的行動裝置和手機，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="6788f-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="6788f-107">在下圖中，使用者 Irena 有兩個端點：</span><span class="sxs-lookup"><span data-stu-id="6788f-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="6788f-108">團隊端點</span><span class="sxs-lookup"><span data-stu-id="6788f-108">A Teams endpoint</span></span>
- <span data-ttu-id="6788f-109">連接至協力廠商 SBC 的 SIP 電話</span><span class="sxs-lookup"><span data-stu-id="6788f-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="6788f-110">當來電到達時，SBC 會將電話系統 Direct 路由和協力廠商 SBC 之間的呼叫派生。</span><span class="sxs-lookup"><span data-stu-id="6788f-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![顯示分叉團隊端點的圖表](media/direct-routing-call-notification-1.png)

<span data-ttu-id="6788f-112">如果在分叉2（由協力廠商 SBC）接受呼叫，小組會產生「未接來電」通知。</span><span class="sxs-lookup"><span data-stu-id="6788f-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="6788f-113">您可以將 SBC 設定為在分叉1上傳送取消，以避免「未接來電」通知，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6788f-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="6788f-114">原因： SIP;原因 = 200; 文字「通話完成于別處」</span><span class="sxs-lookup"><span data-stu-id="6788f-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="6788f-115">請注意，通話不會在 Microsoft Phone 系統的通話詳細資料記錄中登入，因為這是成功的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6788f-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="6788f-116">呼叫將會註冊為「嘗試」，其最終 SIP 程式碼為「487」、最終的 Microsoft 子代碼 "540200"，以及最後一個 SIP 程式碼片語「在別處完成通話」。</span><span class="sxs-lookup"><span data-stu-id="6788f-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="6788f-117">（若要查看通話明細記錄，請移至 [團隊管理員] 入口網站、[分析] 和 [報表] 的使用方式報告，然後選取 [PSNT 使用量]。）</span><span class="sxs-lookup"><span data-stu-id="6788f-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSNT Usage.)</span></span>


<span data-ttu-id="6788f-118">下圖說明分叉1的 SIP 階梯，說明通話流程，以及取消訊息中的預期原因。</span><span class="sxs-lookup"><span data-stu-id="6788f-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![顯示分叉團隊端點的圖表](media/direct-routing-call-notification-2.png)
