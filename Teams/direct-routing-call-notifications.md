---
title: 電話系統直接路由
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
f1.keywords:
- NOCSH
description: 直接路由通話通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341803"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="edf15-103">管理來電通知</span><span class="sxs-lookup"><span data-stu-id="edf15-103">Manage call notifications</span></span>

<span data-ttu-id="edf15-104">本文將說明如何管理使用者的通話通知。</span><span class="sxs-lookup"><span data-stu-id="edf15-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="edf15-105">您可以將呼叫端點設定為協力廠商Teams或協力廠商私人分支 Exchange (PBX) 或會話邊界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="edf15-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="edf15-106">例如，如果您想要同時將電話傳送至使用者的行動電話和電話機，這項功能就很有用。</span><span class="sxs-lookup"><span data-stu-id="edf15-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="edf15-107">在下列圖表中，使用者 Irena 有兩個端點：</span><span class="sxs-lookup"><span data-stu-id="edf15-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="edf15-108">Teams端點</span><span class="sxs-lookup"><span data-stu-id="edf15-108">A Teams endpoint</span></span>
- <span data-ttu-id="edf15-109">已連接至協力廠商 SBC 的 SIP 電話</span><span class="sxs-lookup"><span data-stu-id="edf15-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="edf15-110">當來電到達時，SBC 會電話系統直接路由和協力廠商 SBC 之間的通話。</span><span class="sxs-lookup"><span data-stu-id="edf15-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![顯示分叉端點Teams圖表](media/direct-routing-call-notification-1.png)

<span data-ttu-id="edf15-112">如果協力廠商 SBC (在 fork 2 上接受) ，Teams就會產生「未接來電」通知。</span><span class="sxs-lookup"><span data-stu-id="edf15-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="edf15-113">您可以按照以下方式，將 SBC 在 Fork 1 上傳送 Cancel，以防止「未接來電」通知：</span><span class="sxs-lookup"><span data-stu-id="edf15-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="edf15-114">原因：SIP;cause=200;text"通話在其他地方完成」</span><span class="sxs-lookup"><span data-stu-id="edf15-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="edf15-115">請注意，通話不會在系統通話詳細Microsoft 電話記錄中註冊為成功的通話。</span><span class="sxs-lookup"><span data-stu-id="edf15-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="edf15-116">通話會以 「嘗試」註冊為「嘗試」，包含 「487」、「540200」的最終 Microsoft 子代碼，以及「在其他地方完成通話」的最後 SIP 程式碼片語。</span><span class="sxs-lookup"><span data-stu-id="edf15-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="edf15-117"> (若要查看通話詳細資料記錄，請前往 [Teams 系統管理入口網站、分析與報告、使用方式報告，然後選取 [PSTN 使用方式) </span><span class="sxs-lookup"><span data-stu-id="edf15-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="edf15-118">下圖說明 Fork 1 的 SIP 梯級，說明通話流程，以及取消訊息中的預期原因。</span><span class="sxs-lookup"><span data-stu-id="edf15-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![顯示分叉端點Teams圖表](media/direct-routing-call-notification-2.png)
