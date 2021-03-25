---
title: Teams Voice Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121301"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="0f62d-103">Contoso 案例研究：音訊會議</span><span class="sxs-lookup"><span data-stu-id="0f62d-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="0f62d-104">若要瞭解音訊會議是什麼、費用、可用性及運作方式 &mdash; ，Contoso 已審閱 Office &mdash; [365](deploy-audio-conferencing-teams-landing-page.md)的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="0f62d-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="0f62d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="0f62d-105">Overview</span></span> 

<span data-ttu-id="0f62d-106">對於音訊會議，Contoso 會使用組織中以及外部都已知的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0f62d-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="0f62d-107">由於 Contoso 想要盡可能維護這些號碼，因此他們審閱了將專用和共用電話號碼指派給音訊會議橋接器的資訊。</span><span class="sxs-lookup"><span data-stu-id="0f62d-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="0f62d-108">Contoso 根據他們的研究做出下列決定：</span><span class="sxs-lookup"><span data-stu-id="0f62d-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="0f62d-109">只有定期主持音訊會議通話的一部分人口會收到音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="0f62d-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="0f62d-110">Contoso 會使用專用電話號碼，並移植現有的號碼，以用於音訊會議。</span><span class="sxs-lookup"><span data-stu-id="0f62d-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="0f62d-111">由於 Contoso 使用者使用的是商務用 Skype，而且所有使用者的信箱都位於線上，因此許多使用者已排程現有的會議。</span><span class="sxs-lookup"><span data-stu-id="0f62d-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="0f62d-112">Contoso 閱讀使用會議移 ([MMS) ， ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) 以瞭解當將使用者變更為 TeamsOnly 模式時，系統會自動更新 Contoso 的現有會議。</span><span class="sxs-lookup"><span data-stu-id="0f62d-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="0f62d-113">配置</span><span class="sxs-lookup"><span data-stu-id="0f62d-113">Configuration</span></span>

<span data-ttu-id="0f62d-114">與音訊會議相關聯的電話號碼稱為電話系統內的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0f62d-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="0f62d-115">對於使用通話方案的位置，若要將現有的電話號碼從電話電信公司移植到 Office 365，Contoso 會遵循取得服務電話號碼 [中的步驟](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="0f62d-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="0f62d-116">若要在技術試驗中指派音訊會議授權給使用者，Contoso 系統管理員遵循管理貴組織的音訊會議設定 [中的步驟](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0f62d-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="0f62d-117">針對商務試驗和移移，Contoso 會遵循 Azure Active Directory 中的群組成員資格指派授權給使用者中的步驟，來使用 [群組式授權](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="0f62d-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

