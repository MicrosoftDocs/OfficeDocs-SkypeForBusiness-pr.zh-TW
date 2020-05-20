---
title: 呼叫 & 會議的小組原則錄製簡介
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 瞭解團隊原則錄製，以便通話 & 會議
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294048"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="e1c98-103">Callings & 會議的小組原則錄製簡介</span><span class="sxs-lookup"><span data-stu-id="e1c98-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="e1c98-104">原則式錄製：可讓使用管理原則的 Microsoft 團隊運用 Microsoft 團隊進行通話和會議，以便在相關的公司或法規原則所需的後續處理及保留期間自動錄製並捕獲。</span><span class="sxs-lookup"><span data-stu-id="e1c98-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="e1c98-105">團隊已增強，可支援協力廠商錄製解決方案的整合，包括平臺功能、使用者體驗和管理介面，以提供用於設定、管理、錄製、儲存及分析團隊溝通的端對端方案。</span><span class="sxs-lookup"><span data-stu-id="e1c98-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="e1c98-106">這包括通訊平臺 Api 和錄製事件，提供：</span><span class="sxs-lookup"><span data-stu-id="e1c98-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="e1c98-107">跨裝置的無縫、高品質媒體捕獲，以及音訊、影片、螢幕共用及聊天的所有支援端點。</span><span class="sxs-lookup"><span data-stu-id="e1c98-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="e1c98-108">支援小組使用者與支援的呼叫端點之間的互動捕獲（團隊、團隊行動裝置、商務用 Skype、PSTN）</span><span class="sxs-lookup"><span data-stu-id="e1c98-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="e1c98-109">新的合規性記錄管理原則，包括與現有團隊的整合管理通話與會議工具及原則</span><span class="sxs-lookup"><span data-stu-id="e1c98-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="e1c98-110">針對有個別授權的小組使用者啟用</span><span class="sxs-lookup"><span data-stu-id="e1c98-110">Enabled for Teams users with a separate license</span></span>

<span data-ttu-id="e1c98-111">相容性錄製解決方案整合功能也會在 Ignite 2019 的[<span class="underline">相容性錄製和 Microsoft 團隊會話</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)中進行審查。</span><span class="sxs-lookup"><span data-stu-id="e1c98-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="e1c98-112">團隊互動錄製概覽</span><span class="sxs-lookup"><span data-stu-id="e1c98-112">Teams interaction recording overview</span></span>

<span data-ttu-id="e1c98-113">互動錄製使用案例可以有效地分為四種主要類別的錄製功能-便利性、功能、組織及法律截獲，如影像所示：</span><span class="sxs-lookup"><span data-stu-id="e1c98-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="e1c98-114">![螢幕擷取畫面顯示互動錄製的內容和原因。](media/recording-taxonomy.png "影像會顯示錄製類別。")</span><span class="sxs-lookup"><span data-stu-id="e1c98-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="e1c98-115">每個類別都必須對啟動錄製的方式有不同的需求、錄製的內容、儲存錄製的位置、通知者、控制存取的人員，以及如何處理保留作業。</span><span class="sxs-lookup"><span data-stu-id="e1c98-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="e1c98-116">便利性</span><span class="sxs-lookup"><span data-stu-id="e1c98-116">Convenience</span></span>        | <span data-ttu-id="e1c98-117">多功能</span><span class="sxs-lookup"><span data-stu-id="e1c98-117">Functional</span></span>         | <span data-ttu-id="e1c98-118">組織-一般</span><span class="sxs-lookup"><span data-stu-id="e1c98-118">Org - General</span></span>      | <span data-ttu-id="e1c98-119">組織管制</span><span class="sxs-lookup"><span data-stu-id="e1c98-119">Org - Regulated</span></span> | <span data-ttu-id="e1c98-120">法律截獲</span><span class="sxs-lookup"><span data-stu-id="e1c98-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="e1c98-121">發送</span><span class="sxs-lookup"><span data-stu-id="e1c98-121">Initiator</span></span>              | <span data-ttu-id="e1c98-122">使用者</span><span class="sxs-lookup"><span data-stu-id="e1c98-122">User</span></span>               | <span data-ttu-id="e1c98-123">App/解決方案</span><span class="sxs-lookup"><span data-stu-id="e1c98-123">App/Solution</span></span>       | <span data-ttu-id="e1c98-124">系統管理員（系統）</span><span class="sxs-lookup"><span data-stu-id="e1c98-124">Admin (system)</span></span>     | <span data-ttu-id="e1c98-125">系統管理員（系統）</span><span class="sxs-lookup"><span data-stu-id="e1c98-125">Admin (system)</span></span>  | <span data-ttu-id="e1c98-126">LEA</span><span class="sxs-lookup"><span data-stu-id="e1c98-126">LEA</span></span>                |
| <span data-ttu-id="e1c98-127">目標</span><span class="sxs-lookup"><span data-stu-id="e1c98-127">Target</span></span>                 | <span data-ttu-id="e1c98-128">每次通話/會議</span><span class="sxs-lookup"><span data-stu-id="e1c98-128">Per-call / meeting</span></span> | <span data-ttu-id="e1c98-129">每次通話/會議</span><span class="sxs-lookup"><span data-stu-id="e1c98-129">Per-call / meeting</span></span> | <span data-ttu-id="e1c98-130">每次通話/會議</span><span class="sxs-lookup"><span data-stu-id="e1c98-130">Per-call / meeting</span></span> | <span data-ttu-id="e1c98-131">每位使用者</span><span class="sxs-lookup"><span data-stu-id="e1c98-131">Per-user</span></span>        | <span data-ttu-id="e1c98-132">每個端點/已執行</span><span class="sxs-lookup"><span data-stu-id="e1c98-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="e1c98-133">儲存擁有者</span><span class="sxs-lookup"><span data-stu-id="e1c98-133">Storage owner</span></span>          | <span data-ttu-id="e1c98-134">使用者</span><span class="sxs-lookup"><span data-stu-id="e1c98-134">User</span></span>               | <span data-ttu-id="e1c98-135">適用</span><span class="sxs-lookup"><span data-stu-id="e1c98-135">App</span></span>                | <span data-ttu-id="e1c98-136">管理員</span><span class="sxs-lookup"><span data-stu-id="e1c98-136">Admin</span></span>              | <span data-ttu-id="e1c98-137">從屬</span><span class="sxs-lookup"><span data-stu-id="e1c98-137">Compliance</span></span>      | <span data-ttu-id="e1c98-138">LEA</span><span class="sxs-lookup"><span data-stu-id="e1c98-138">LEA</span></span>                |
| <span data-ttu-id="e1c98-139">需要通知嗎？</span><span class="sxs-lookup"><span data-stu-id="e1c98-139">Notification required?</span></span> | <span data-ttu-id="e1c98-140">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-140">Yes</span></span>                | <span data-ttu-id="e1c98-141">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-141">Yes</span></span>                | <span data-ttu-id="e1c98-142">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-142">Yes</span></span>                | <span data-ttu-id="e1c98-143">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-143">Yes</span></span>             | <span data-ttu-id="e1c98-144">否</span><span class="sxs-lookup"><span data-stu-id="e1c98-144">No</span></span>                 |
| <span data-ttu-id="e1c98-145">Access 擁有者</span><span class="sxs-lookup"><span data-stu-id="e1c98-145">Access Owner</span></span>           | <span data-ttu-id="e1c98-146">使用者</span><span class="sxs-lookup"><span data-stu-id="e1c98-146">User</span></span>               | <span data-ttu-id="e1c98-147">適用</span><span class="sxs-lookup"><span data-stu-id="e1c98-147">App</span></span>                | <span data-ttu-id="e1c98-148">管理員</span><span class="sxs-lookup"><span data-stu-id="e1c98-148">Admin</span></span>              | <span data-ttu-id="e1c98-149">從屬</span><span class="sxs-lookup"><span data-stu-id="e1c98-149">Compliance</span></span>      | <span data-ttu-id="e1c98-150">LEA</span><span class="sxs-lookup"><span data-stu-id="e1c98-150">LEA</span></span>                |
| <span data-ttu-id="e1c98-151">保留原則？</span><span class="sxs-lookup"><span data-stu-id="e1c98-151">Retention Policy?</span></span>      | <span data-ttu-id="e1c98-152">選用</span><span class="sxs-lookup"><span data-stu-id="e1c98-152">Optional</span></span>           | <span data-ttu-id="e1c98-153">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-153">Yes</span></span>                | <span data-ttu-id="e1c98-154">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-154">Yes</span></span>                | <span data-ttu-id="e1c98-155">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-155">Yes</span></span>             | <span data-ttu-id="e1c98-156">是</span><span class="sxs-lookup"><span data-stu-id="e1c98-156">Yes</span></span>                |

<span data-ttu-id="e1c98-157">小組提供各種功能，可讓會議與即時事件進行[<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording)且正常運作。</span><span class="sxs-lookup"><span data-stu-id="e1c98-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="e1c98-158">組織錄製意味著讓使用團隊進行呼叫與會議 stipulate、使用管理原則進行通話與線上會議時，應依相關的公司或法規原則，自動錄製並捕獲進行後續處理及保留的方式。</span><span class="sxs-lookup"><span data-stu-id="e1c98-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="e1c98-159">此原則下的使用者會發現與小組的數位互動正在錄製，但無法停用錄製，而且在互動完成之後就不能存取錄製。</span><span class="sxs-lookup"><span data-stu-id="e1c98-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="e1c98-160">錄製成為組織封存的一部分，可供電子檔探索、法律封存及其他公司留存用途使用。</span><span class="sxs-lookup"><span data-stu-id="e1c98-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="e1c98-161">使用者需求範例</span><span class="sxs-lookup"><span data-stu-id="e1c98-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e1c98-162"><strong>個人</strong></span><span class="sxs-lookup"><span data-stu-id="e1c98-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="e1c98-163"><strong>滿足</strong></span><span class="sxs-lookup"><span data-stu-id="e1c98-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e1c98-164">錄製的使用者</span><span class="sxs-lookup"><span data-stu-id="e1c98-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e1c98-165">在進行錄製時收到通知。</span><span class="sxs-lookup"><span data-stu-id="e1c98-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-166">在原則與/或記錄器錯誤導致通話行為變更時收到通知。</span><span class="sxs-lookup"><span data-stu-id="e1c98-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c98-167">通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="e1c98-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e1c98-168">瞭解為何以及如何將錄製原則套用/強制執行至團隊使用者/端點。</span><span class="sxs-lookup"><span data-stu-id="e1c98-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-169">設定及維護組織的小組記錄原則。</span><span class="sxs-lookup"><span data-stu-id="e1c98-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-170">監視及疑難排解與團隊通話與會議有關的錄製相關問題。</span><span class="sxs-lookup"><span data-stu-id="e1c98-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-171">針對使用方式、品質和可靠性，支援內部合規性監察官與操作分析。</span><span class="sxs-lookup"><span data-stu-id="e1c98-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c98-172">合規性監察官</span><span class="sxs-lookup"><span data-stu-id="e1c98-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e1c98-173">收集所有團隊通訊的方式，以符合適當地區界限中的合規性義務所需的方式。</span><span class="sxs-lookup"><span data-stu-id="e1c98-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-174">根據與通訊相關的中繼資料或互動內容來搜尋互動。</span><span class="sxs-lookup"><span data-stu-id="e1c98-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="e1c98-175">常見的範例包括：</span><span class="sxs-lookup"><span data-stu-id="e1c98-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1c98-176"><strong>中繼資料</strong> -參與者、時間、方向、撥電話號碼、來源編號、自訂商務資料</span><span class="sxs-lookup"><span data-stu-id="e1c98-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="e1c98-177"><strong>內容</strong>–操作、觀點、拼音、相關互動</span><span class="sxs-lookup"><span data-stu-id="e1c98-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="e1c98-178">分析收集的通訊並與之互動，包括在收集時監視互動的能力。</span><span class="sxs-lookup"><span data-stu-id="e1c98-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="e1c98-179">確保收集的通訊安全，並防止所有階段遭到篡改。</span><span class="sxs-lookup"><span data-stu-id="e1c98-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="e1c98-180">方案架構概述</span><span class="sxs-lookup"><span data-stu-id="e1c98-180">Solution architecture overview</span></span>

<span data-ttu-id="e1c98-181">合規性錄製解決方案已與團隊整合，如下列圖表所示：</span><span class="sxs-lookup"><span data-stu-id="e1c98-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="e1c98-182">![顯示小組自訂應用程式設定的螢幕擷取畫面](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像會顯示當您傳送和接收小組會議或通話時的流程。")</span><span class="sxs-lookup"><span data-stu-id="e1c98-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="e1c98-183">燒錄</span><span class="sxs-lookup"><span data-stu-id="e1c98-183">Recorder</span></span>

<span data-ttu-id="e1c98-184">[規範錄製] 解決方案的核心元件是錄影機。</span><span class="sxs-lookup"><span data-stu-id="e1c98-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="e1c98-185">錄影機是以可伸縮的 Azure 服務（bot）建立的，可[<span class="underline">利用 microsoft 的通訊平臺</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview)，並使用 microsoft Graph 將其註冊為應用程式。</span><span class="sxs-lookup"><span data-stu-id="e1c98-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="e1c98-186">記錄器提供與團隊通話與會議[<span class="underline">通訊平臺 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的直接互動，並提供媒體攝取的端點。</span><span class="sxs-lookup"><span data-stu-id="e1c98-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="e1c98-187">[<span class="underline">提供範例規範記錄器應用程式</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot)，說明如何設定 bot、建立 app 實例並指派合規性原則。</span><span class="sxs-lookup"><span data-stu-id="e1c98-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="e1c98-188">此範例也會提供用於錄製特定互動（例如處理[<span class="underline">撥入電話</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   路由、[<span class="underline">變更錄製狀態</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)，以及[<span class="underline">移除錄製的使用者</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)）的 API 用法範例。</span><span class="sxs-lookup"><span data-stu-id="e1c98-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="e1c98-189">您可以在這裡找到適用于[<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)和[<span class="underline">IncomingCoNtext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)的特定 api 的圖形檔。</span><span class="sxs-lookup"><span data-stu-id="e1c98-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="e1c98-190">記錄器服務的確切實現會因合作夥伴而異，但必須設計為支援多個燒錄機，才能實現高可用性和地理位置分佈，以減少團隊的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="e1c98-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="e1c98-191">此外，預期記錄器本身在設計時應考慮復原能力和冗余性。</span><span class="sxs-lookup"><span data-stu-id="e1c98-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="e1c98-192">在提交其認證方案前，合作夥伴必須先確認 Microsoft Graph 通訊 Api 與 Sdk 的最低發行版本本，然後才能提交其認證方案，以確保所有合規性錄製整合需求都受到支援。</span><span class="sxs-lookup"><span data-stu-id="e1c98-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="e1c98-193">針對合規性錄製案例的基本需求，有兩個特殊需求：</span><span class="sxs-lookup"><span data-stu-id="e1c98-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="e1c98-194">錄影機 bot 必須部署在 Azure 中</span><span class="sxs-lookup"><span data-stu-id="e1c98-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="e1c98-195">錄影機 bot 必須在 Azure 中的 Windows VM 上執行</span><span class="sxs-lookup"><span data-stu-id="e1c98-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="e1c98-196">Azure 和 Windows VM 的需求只適用于 [團隊 Bot] 元件，這表示合作夥伴可能會執行其選擇的其他平臺，前提是他們可以滿足相容性錄製的相關效能與功能需求。</span><span class="sxs-lookup"><span data-stu-id="e1c98-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="e1c98-197">合規性錄製原則指派與置備</span><span class="sxs-lookup"><span data-stu-id="e1c98-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="e1c98-198">IT 管理員可以透過建立並指派合規性錄製原則，來判斷要錄製哪些使用者，以及每個使用者要使用哪一種記錄器。</span><span class="sxs-lookup"><span data-stu-id="e1c98-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="e1c98-199">當通訊互動發生時，會根據這些原則的設定，自動邀請錄影機參與交談。</span><span class="sxs-lookup"><span data-stu-id="e1c98-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="e1c98-200">合規性錄製原則是使用[<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)來管理，而且可以針對每個組織在租使用者層級套用。</span><span class="sxs-lookup"><span data-stu-id="e1c98-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant and per-user level for each organization.</span></span> <span data-ttu-id="e1c98-201">您可以在 [[<span class="underline">會議原則</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)] 和 [[<span class="underline">通話原則</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)] 中找到更多關於 Microsoft 檔的資訊。</span><span class="sxs-lookup"><span data-stu-id="e1c98-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) and [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span></span>

1. <span data-ttu-id="e1c98-202">在您的租使用者中建立應用程式實例。</span><span class="sxs-lookup"><span data-stu-id="e1c98-202">Create an application instance in your tenant.</span></span>

```powershell
PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
UserPrincipalName : cr.instance@contoso.onmicrosoft.com
ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
DisplayName       : ComplianceRecordingBotInstance
PhoneNumber       :
```

```powershell
PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

2. <span data-ttu-id="e1c98-203">建立合規性錄製原則。</span><span class="sxs-lookup"><span data-stu-id="e1c98-203">Create a Compliance Recording policy.</span></span>

```powershell
PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

Identity                        : Global
ComplianceRecordingApplications : {}
Enabled                         : True
WarnUserOnRemoval               : True
Description                     : Test policy created by tenant admin
```

```powershell
PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
-ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="e1c98-204">將合規性錄製原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e1c98-204">Assign the Compliance Recording policy to a user.</span></span>

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a><span data-ttu-id="e1c98-205">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="e1c98-205">User experiences</span></span>

<span data-ttu-id="e1c98-206">已使用團隊用戶端體驗來啟用通知支援。</span><span class="sxs-lookup"><span data-stu-id="e1c98-206">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="e1c98-207">體驗可以是 [視覺] 或 [音訊]。</span><span class="sxs-lookup"><span data-stu-id="e1c98-207">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="e1c98-208">**團隊用戶端-視覺通知**</span><span class="sxs-lookup"><span data-stu-id="e1c98-208">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="e1c98-209">桌面/網頁</span><span class="sxs-lookup"><span data-stu-id="e1c98-209">Desktop/web</span></span>
- <span data-ttu-id="e1c98-210">行動裝置（iOS/Android）</span><span class="sxs-lookup"><span data-stu-id="e1c98-210">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="e1c98-211">團隊手機</span><span class="sxs-lookup"><span data-stu-id="e1c98-211">Teams phones</span></span>
- <span data-ttu-id="e1c98-212">團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="e1c98-212">Teams rooms</span></span>

<span data-ttu-id="e1c98-213">**其他端點-音訊通知**</span><span class="sxs-lookup"><span data-stu-id="e1c98-213">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="e1c98-214">SIP 電話</span><span class="sxs-lookup"><span data-stu-id="e1c98-214">SIP phones</span></span>
- <span data-ttu-id="e1c98-215">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e1c98-215">Skype for Business</span></span>
- <span data-ttu-id="e1c98-216">音訊會議</span><span class="sxs-lookup"><span data-stu-id="e1c98-216">Audio conferencing</span></span>
- <span data-ttu-id="e1c98-217">PSTN 呼叫者</span><span class="sxs-lookup"><span data-stu-id="e1c98-217">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="e1c98-218">小組認證程式的合規性錄製</span><span class="sxs-lookup"><span data-stu-id="e1c98-218">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="e1c98-219">除了發佈公開提供的 Api，讓合作夥伴能夠開發並整合 CCaaS 方案與團隊合作，我們已開發出 Microsoft 團隊認證計畫的規範錄製，為客戶提供每個參與合作夥伴的解決方案都經過測試和驗證，以提供他們預期的品質、相容性及可靠性。</span><span class="sxs-lookup"><span data-stu-id="e1c98-219">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="e1c98-220">下列合作夥伴正在為 Microsoft 團隊驗證其解決方案的程式。</span><span class="sxs-lookup"><span data-stu-id="e1c98-220">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="e1c98-221">Partner</span><span class="sxs-lookup"><span data-stu-id="e1c98-221">Partner</span></span>|<span data-ttu-id="e1c98-222">解決方案網站</span><span class="sxs-lookup"><span data-stu-id="e1c98-222">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="e1c98-223">ASC 技術</span><span class="sxs-lookup"><span data-stu-id="e1c98-223">ASC Technologies</span></span> |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|<span data-ttu-id="e1c98-224">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e1c98-224">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="e1c98-225">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="e1c98-225">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="e1c98-226">！</span><span class="sxs-lookup"><span data-stu-id="e1c98-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="e1c98-227">Numonix</span><span class="sxs-lookup"><span data-stu-id="e1c98-227">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="e1c98-228">紅色方塊</span><span class="sxs-lookup"><span data-stu-id="e1c98-228">Red Box</span></span> |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|<span data-ttu-id="e1c98-229">Verint</span><span class="sxs-lookup"><span data-stu-id="e1c98-229">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="e1c98-230">此清單會隨著更多合作夥伴加入並符合認證準則而更新。</span><span class="sxs-lookup"><span data-stu-id="e1c98-230">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1c98-231">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e1c98-231">Next steps</span></span>

<span data-ttu-id="e1c98-232">如果您是尋求加入認證計畫的供應商，請寄出郵件<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a></span><span class="sxs-lookup"><span data-stu-id="e1c98-232">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a></span></span>
