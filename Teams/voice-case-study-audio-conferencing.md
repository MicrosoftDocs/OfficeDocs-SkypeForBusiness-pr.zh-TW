---
title: 團隊語音 Contoso 案例研究
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
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785982"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="0b249-103">Contoso 案例研究：音訊會議</span><span class="sxs-lookup"><span data-stu-id="0b249-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="0b249-104">若要瞭解音訊會議的 &mdash; 內容、其成本、可用性，以及它如何運作， &mdash; Contoso[在 Office 365 中審查音訊會議](deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="0b249-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="0b249-105">概觀</span><span class="sxs-lookup"><span data-stu-id="0b249-105">Overview</span></span> 

<span data-ttu-id="0b249-106">對於音訊會議，Contoso 在組織內以及外部使用的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0b249-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="0b249-107">由於 Contoso 想要盡可能保留這些數位，因此他們已複習將專用和共用電話號碼指派給音訊會議橋接器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0b249-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="0b249-108">根據其研究，Contoso 進行下列決策：</span><span class="sxs-lookup"><span data-stu-id="0b249-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="0b249-109">只有定期託管音訊會議呼叫的一部分人口，才會收到音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="0b249-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="0b249-110">Contoso 會使用專用的電話號碼，並將其現有的號碼與音訊會議搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0b249-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="0b249-111">因為 Contoso 使用者使用的是商務用 Skype，且所有使用者的信箱都在線上，所以許多使用者已安排現有的會議。</span><span class="sxs-lookup"><span data-stu-id="0b249-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="0b249-112">Contoso 已[使用會議遷移服務（MMS）](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)進行閱讀，以瞭解在將使用者變更為 TeamsOnly 模式時，會自動為 Contoso 更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="0b249-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="0b249-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="0b249-113">Configuration</span></span>

<span data-ttu-id="0b249-114">與音訊會議相關聯的電話號碼稱為電話系統中的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0b249-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="0b249-115">針對使用通話方案的位置，若要將其電話載波中的現有電話號碼移植至 Office 365，Contoso 請按照[取得服務電話號碼](getting-service-phone-numbers.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="0b249-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="0b249-116">若要將音訊會議授權指派給技術試驗中的最終使用者，Contoso 管理員請按照[管理貴組織的音訊會議設定](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)中的步驟操作。</span><span class="sxs-lookup"><span data-stu-id="0b249-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="0b249-117">針對業務試驗與遷移，Contoso 使用以群組為基礎的授權，請按照在[Azure Active Directory 中的群組成員資格指派授權給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="0b249-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 