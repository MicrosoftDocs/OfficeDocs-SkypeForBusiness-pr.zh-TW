---
title: 會議通話的 Teams 策略型錄製簡介&簡介
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 瞭解會議通話的 Teams &錄製
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
ms.openlocfilehash: 7972febeab134f0ec075418e351c35ef7e273fcf
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439668"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="f1722-103">會議通話的 Teams &簡介</span><span class="sxs-lookup"><span data-stu-id="f1722-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="f1722-104">以策略為基礎的錄製可讓採用 Microsoft Teams 進行通話和會議的組織，使用系統管理政策，自動錄製和捕獲通話和線上會議，以按照相關公司或法規政策的要求進行後續處理和保留。</span><span class="sxs-lookup"><span data-stu-id="f1722-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="f1722-105">Teams 已經過增強，可支援整合協力廠商錄製解決方案，包括平臺功能、使用者體驗，以及提供端對端解決方案所需的系統管理介面，以用於配置、管理、錄製、儲存及分析 Teams 通訊。</span><span class="sxs-lookup"><span data-stu-id="f1722-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="f1722-106">增強功能包括通訊平臺 API 和錄製事件，提供：</span><span class="sxs-lookup"><span data-stu-id="f1722-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="f1722-107">跨裝置及所有支援的音訊、視像、螢幕分享和聊天端點，順暢、高品質的媒體捕獲。</span><span class="sxs-lookup"><span data-stu-id="f1722-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="f1722-108">支援 Teams 使用者與支援的通話端點之間的互動 (Teams、Teams Mobile、商務用 Skype、PSTN) </span><span class="sxs-lookup"><span data-stu-id="f1722-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="f1722-109">合規性錄製的新系統管理政策，包括與現有的 Teams 系統管理通話和會議工具與政策整合</span><span class="sxs-lookup"><span data-stu-id="f1722-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="f1722-110">Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3/E5 使用者可以啟用合規性錄製功能。</span><span class="sxs-lookup"><span data-stu-id="f1722-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="f1722-111">合規性錄製解決方案整合功能也于 Ignite 2019 的合規性錄製和 Microsoft Teams 會話中 [<span class="underline">受到審查</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。</span><span class="sxs-lookup"><span data-stu-id="f1722-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="f1722-112">Teams 互動錄製概觀</span><span class="sxs-lookup"><span data-stu-id="f1722-112">Teams interaction recording overview</span></span>

<span data-ttu-id="f1722-113">互動錄製使用案例可以有效分成四個主要的錄製功能類別 ：便利性、功能、組織及合法截取，如影像所示：</span><span class="sxs-lookup"><span data-stu-id="f1722-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="f1722-114">![顯示互動錄製內容與原因的螢幕擷取畫面。](media/recording-taxonomy.png "影像顯示錄製類別。")</span><span class="sxs-lookup"><span data-stu-id="f1722-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="f1722-115">每個類別對於錄製的啟動方式、錄製內容、錄製位置、收到通知者、誰控制存取權，以及保留的處理方式，都有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="f1722-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="f1722-116">類型</span><span class="sxs-lookup"><span data-stu-id="f1722-116">Type</span></span>                   | <span data-ttu-id="f1722-117">方便 (一般 Teams 錄製) </span><span class="sxs-lookup"><span data-stu-id="f1722-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="f1722-118">組織 - 受規範 (合規性錄製) </span><span class="sxs-lookup"><span data-stu-id="f1722-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="f1722-119">引發</span><span class="sxs-lookup"><span data-stu-id="f1722-119">Initiator</span></span>              | <span data-ttu-id="f1722-120">使用者</span><span class="sxs-lookup"><span data-stu-id="f1722-120">User</span></span>               | <span data-ttu-id="f1722-121">系統 (系統) </span><span class="sxs-lookup"><span data-stu-id="f1722-121">Admin (system)</span></span>  |
| <span data-ttu-id="f1722-122">目標</span><span class="sxs-lookup"><span data-stu-id="f1722-122">Target</span></span>                 | <span data-ttu-id="f1722-123">每通話/會議</span><span class="sxs-lookup"><span data-stu-id="f1722-123">Per-call / meeting</span></span> | <span data-ttu-id="f1722-124">每個使用者</span><span class="sxs-lookup"><span data-stu-id="f1722-124">Per-user</span></span>        |
| <span data-ttu-id="f1722-125">儲存空間擁有者</span><span class="sxs-lookup"><span data-stu-id="f1722-125">Storage owner</span></span>          | <span data-ttu-id="f1722-126">使用者</span><span class="sxs-lookup"><span data-stu-id="f1722-126">User</span></span>               | <span data-ttu-id="f1722-127">合規性</span><span class="sxs-lookup"><span data-stu-id="f1722-127">Compliance</span></span>      |
| <span data-ttu-id="f1722-128">需要通知嗎？</span><span class="sxs-lookup"><span data-stu-id="f1722-128">Notification required?</span></span> | <span data-ttu-id="f1722-129">是</span><span class="sxs-lookup"><span data-stu-id="f1722-129">Yes</span></span>                | <span data-ttu-id="f1722-130">是</span><span class="sxs-lookup"><span data-stu-id="f1722-130">Yes</span></span>             |
| <span data-ttu-id="f1722-131">Access 擁有者</span><span class="sxs-lookup"><span data-stu-id="f1722-131">Access Owner</span></span>           | <span data-ttu-id="f1722-132">使用者</span><span class="sxs-lookup"><span data-stu-id="f1722-132">User</span></span>               | <span data-ttu-id="f1722-133">合規性</span><span class="sxs-lookup"><span data-stu-id="f1722-133">Compliance</span></span>      |
| <span data-ttu-id="f1722-134">保留政策？</span><span class="sxs-lookup"><span data-stu-id="f1722-134">Retention Policy?</span></span>      | <span data-ttu-id="f1722-135">選用</span><span class="sxs-lookup"><span data-stu-id="f1722-135">Optional</span></span>           | <span data-ttu-id="f1722-136">是</span><span class="sxs-lookup"><span data-stu-id="f1722-136">Yes</span></span>             |

<span data-ttu-id="f1722-137">Teams 提供各種功能，方便 [<span class="underline">且</span>](./cloud-recording.md) 實用的會議與即時活動錄製。</span><span class="sxs-lookup"><span data-stu-id="f1722-137">Teams provides various capabilities for [<span class="underline">convenient</span>](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="f1722-138">組織錄製是指讓採用 Teams 通話和會議的組織，以系統管理政策的方式，自動錄製和捕獲通話和線上會議，以便根據相關公司或法規政策的要求進行後續處理和保留。</span><span class="sxs-lookup"><span data-stu-id="f1722-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="f1722-139">根據此政策的使用者會發現，正在錄製與 Teams 的數位互動，但無法停用錄製，且一旦互動完成，將無法存取錄製。</span><span class="sxs-lookup"><span data-stu-id="f1722-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="f1722-140">錄製成為適用于 eDiscovery、法律保留及其他公司保留用途之合規性和法務人員使用之組織檔案的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1722-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="f1722-141">範例使用者需求</span><span class="sxs-lookup"><span data-stu-id="f1722-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f1722-142"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="f1722-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="f1722-143"><strong>需要</strong></span><span class="sxs-lookup"><span data-stu-id="f1722-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f1722-144">錄製的使用者</span><span class="sxs-lookup"><span data-stu-id="f1722-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f1722-145">進行錄製時收到通知。</span><span class="sxs-lookup"><span data-stu-id="f1722-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="f1722-146">當策略和/或答錄機錯誤導致通話行為變更時，請通知。</span><span class="sxs-lookup"><span data-stu-id="f1722-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1722-147">通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1722-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f1722-148">瞭解為什麼以及如何將錄製原則適用于 Teams 使用者/端點。</span><span class="sxs-lookup"><span data-stu-id="f1722-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="f1722-149">為組織設定及維護 Teams 錄製政策。</span><span class="sxs-lookup"><span data-stu-id="f1722-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="f1722-150">監控和疑難排解 Teams 通話和會議錄製相關問題。</span><span class="sxs-lookup"><span data-stu-id="f1722-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="f1722-151">使用使用方式、品質和可靠性的營運分析，支援內部合規性人員。</span><span class="sxs-lookup"><span data-stu-id="f1722-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1722-152">合規性專員</span><span class="sxs-lookup"><span data-stu-id="f1722-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f1722-153">收集所有 Teams 通訊的方式，以在適當的地區邊界符合合規性義務的方式。</span><span class="sxs-lookup"><span data-stu-id="f1722-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="f1722-154">根據與通訊相關的中繼資料或互動內容搜尋互動。</span><span class="sxs-lookup"><span data-stu-id="f1722-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="f1722-155">常見的範例包括：</span><span class="sxs-lookup"><span data-stu-id="f1722-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="f1722-156"><strong>中繼資料</strong> - 參與者、時間、方向、撥號號碼、起始號碼、自訂商務資料</span><span class="sxs-lookup"><span data-stu-id="f1722-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="f1722-157"><strong>內容</strong> – 文字、情緒、語音、相關互動</span><span class="sxs-lookup"><span data-stu-id="f1722-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f1722-158">分析收集的通訊並與其互動，包括收集互動時監控互動的能力。</span><span class="sxs-lookup"><span data-stu-id="f1722-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="f1722-159">確保收集通訊的安全性，並防止所有階段遭到竄改。</span><span class="sxs-lookup"><span data-stu-id="f1722-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="f1722-160">解決方案架構概觀</span><span class="sxs-lookup"><span data-stu-id="f1722-160">Solution architecture overview</span></span>

<span data-ttu-id="f1722-161">合規性錄製解決方案已與 Teams 整合，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="f1722-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="f1722-162">![顯示小組自訂應用程式設定之螢幕擷取畫面](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像顯示 Teams 會議或通話的接收和接收流程。")</span><span class="sxs-lookup"><span data-stu-id="f1722-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="f1722-163">答錄機</span><span class="sxs-lookup"><span data-stu-id="f1722-163">Recorder</span></span>

<span data-ttu-id="f1722-164">合規性錄製解決方案的核心元件是答錄機。</span><span class="sxs-lookup"><span data-stu-id="f1722-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="f1722-165">錄製器是建立為可縮放的 Azure 服務， (機器人) 利用 [<span class="underline">Microsoft</span>](/graph/cloud-communications-concept-overview) 的通訊平臺，並註冊為 Microsoft Graph 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f1722-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="f1722-166">錄製器提供與 Teams 通話和會議通訊平臺 [<span class="underline">API</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 的直接互動，並提供媒體使用端點。</span><span class="sxs-lookup"><span data-stu-id="f1722-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="f1722-167">提供 [<span class="underline">範例合規性記錄器應用程式</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，顯示如何設定 Bot、建立應用程式實例及指派合規性政策。</span><span class="sxs-lookup"><span data-stu-id="f1722-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="f1722-168">範例中也有用於錄製特定互動的 API 使用方式範例，例如處理[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)來電路由、變更[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)錄製狀態，以及移除正在錄製[<span class="underline">的使用者</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。</span><span class="sxs-lookup"><span data-stu-id="f1722-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="f1722-169">您可以在這裡找到特定 API 上的圖形檔，以用於[<span class="underline">updateRecordingStatus 和</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) [<span class="underline">incomingCoNtext。</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="f1722-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="f1722-170">錄製器服務的確切實現會因合作夥伴而異，但必須設計成支援多個答錄機，才能達到部署的高可用性和地理分佈，以降低 Teams 到錄製器的延遲。</span><span class="sxs-lookup"><span data-stu-id="f1722-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="f1722-171">此外，預計錄製器本身在設計時，會考慮復原和重複。</span><span class="sxs-lookup"><span data-stu-id="f1722-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="f1722-172">合作夥伴在提交認證解決方案之前，必須先確認 Microsoft Graph 通訊 API 和 SDK 的最低發行版本本，以確保支援合規性錄製整合的所有需求。</span><span class="sxs-lookup"><span data-stu-id="f1722-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="f1722-173">合規性錄製案例的兩項基本需求為：</span><span class="sxs-lookup"><span data-stu-id="f1722-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="f1722-174">錄製器 Bot 必須部署在 Azure 中</span><span class="sxs-lookup"><span data-stu-id="f1722-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="f1722-175">錄製器 Bot 必須在 Azure 的 Windows VM 上執行</span><span class="sxs-lookup"><span data-stu-id="f1722-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="f1722-176">Azure 和 Windows VM 需求僅適用于 Teams Bot 元件，這表示合作夥伴可以執行他們選擇的其他平臺，但必須符合合規性錄製的相關績效和功能需求。</span><span class="sxs-lookup"><span data-stu-id="f1722-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="f1722-177">合規性錄製策略指派和置備</span><span class="sxs-lookup"><span data-stu-id="f1722-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="f1722-178">IT 系統管理員可以建立和指派合規性錄製政策，決定要錄製哪些使用者，以及每個使用者會使用哪個錄製器。</span><span class="sxs-lookup"><span data-stu-id="f1722-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="f1722-179">當通訊互動發生時，系統會自動根據這些策略的組式邀請錄製者參與交談。</span><span class="sxs-lookup"><span data-stu-id="f1722-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="f1722-180">合規性錄製原則是使用 [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) 管理，並可在每個組織的租使用者、每個使用者和安全性群組層級上加以應用。</span><span class="sxs-lookup"><span data-stu-id="f1722-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="f1722-181">您可以找到有關 Microsoft Docs [<span class="underline">會議政策</span>](./meeting-policies-in-teams.md)、通話 [<span class="underline">策略</span>](./teams-calling-policy.md) 和  [<span class="underline">群群組原則的更多資訊</span>](./assign-policies.md#assign-a-policy-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="f1722-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](./meeting-policies-in-teams.md), [<span class="underline">calling policies</span>](./teams-calling-policy.md) and  [<span class="underline">group policies</span>](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="f1722-182">在租使用者中建立應用程式實例。</span><span class="sxs-lookup"><span data-stu-id="f1722-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="f1722-183">建立合規性錄製政策。</span><span class="sxs-lookup"><span data-stu-id="f1722-183">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="f1722-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f1722-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="f1722-185">指派合規性錄製策略給使用者。</span><span class="sxs-lookup"><span data-stu-id="f1722-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="f1722-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f1722-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="f1722-187">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="f1722-187">User experiences</span></span>

<span data-ttu-id="f1722-188">使用 Teams 用戶端體驗啟用通知支援。</span><span class="sxs-lookup"><span data-stu-id="f1722-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="f1722-189">體驗可以是視覺或音訊。</span><span class="sxs-lookup"><span data-stu-id="f1722-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="f1722-190">**Teams 用戶端 - 視覺注意事項**</span><span class="sxs-lookup"><span data-stu-id="f1722-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="f1722-191">桌面/Web</span><span class="sxs-lookup"><span data-stu-id="f1722-191">Desktop/web</span></span>
- <span data-ttu-id="f1722-192">行動 (iOS/Android) </span><span class="sxs-lookup"><span data-stu-id="f1722-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="f1722-193">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="f1722-193">Teams phones</span></span>
- <span data-ttu-id="f1722-194">Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="f1722-194">Teams rooms</span></span>

<span data-ttu-id="f1722-195">**其他端點 - 音訊注意事項**</span><span class="sxs-lookup"><span data-stu-id="f1722-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="f1722-196">SIP 電話</span><span class="sxs-lookup"><span data-stu-id="f1722-196">SIP phones</span></span>
- <span data-ttu-id="f1722-197">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f1722-197">Skype for Business</span></span>
- <span data-ttu-id="f1722-198">音訊會議</span><span class="sxs-lookup"><span data-stu-id="f1722-198">Audio conferencing</span></span>
- <span data-ttu-id="f1722-199">PSTN 來電者</span><span class="sxs-lookup"><span data-stu-id="f1722-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="f1722-200">Teams 認證計畫合規性錄製</span><span class="sxs-lookup"><span data-stu-id="f1722-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="f1722-201">除了發佈公開可用的 API，讓合作夥伴能夠開發 CCaaS 解決方案並整合 Teams 之外，我們開發 Microsoft Teams 認證計畫的合規性記錄，為客戶提供保證，確保每個參與合作夥伴的解決方案都經過測試與驗證，以提供他們預期從 Microsoft 解決方案獲得的品質、相容性和可靠性。</span><span class="sxs-lookup"><span data-stu-id="f1722-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="f1722-202">下列合作夥伴已認證其 Microsoft Teams 解決方案。</span><span class="sxs-lookup"><span data-stu-id="f1722-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f1722-203">夥伴</span><span class="sxs-lookup"><span data-stu-id="f1722-203">Partner</span></span>|<span data-ttu-id="f1722-204">解決方案網站</span><span class="sxs-lookup"><span data-stu-id="f1722-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f1722-205">ASC 技術</span><span class="sxs-lookup"><span data-stu-id="f1722-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="f1722-206">音訊代碼</span><span class="sxs-lookup"><span data-stu-id="f1722-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="f1722-207">配音器</span><span class="sxs-lookup"><span data-stu-id="f1722-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="f1722-208">好</span><span class="sxs-lookup"><span data-stu-id="f1722-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="f1722-209">下列合作夥伴正在認證其 Microsoft Teams 解決方案。</span><span class="sxs-lookup"><span data-stu-id="f1722-209">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f1722-210">夥伴</span><span class="sxs-lookup"><span data-stu-id="f1722-210">Partner</span></span>|<span data-ttu-id="f1722-211">解決方案網站</span><span class="sxs-lookup"><span data-stu-id="f1722-211">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f1722-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="f1722-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="f1722-213">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="f1722-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="f1722-214">Luware</span><span class="sxs-lookup"><span data-stu-id="f1722-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="f1722-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="f1722-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="f1722-216">奧克創新</span><span class="sxs-lookup"><span data-stu-id="f1722-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="f1722-217">紅色方塊</span><span class="sxs-lookup"><span data-stu-id="f1722-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="f1722-218">Verint</span><span class="sxs-lookup"><span data-stu-id="f1722-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="f1722-219">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="f1722-219">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

<span data-ttu-id="f1722-220">隨著更多合作夥伴加入並符合認證準則，這份清單將會更新。</span><span class="sxs-lookup"><span data-stu-id="f1722-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1722-221">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f1722-221">Next steps</span></span>

<span data-ttu-id="f1722-222">如果您是想加入認證計畫廠商，請寄郵件<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a></span><span class="sxs-lookup"><span data-stu-id="f1722-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
