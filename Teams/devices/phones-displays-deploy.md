---
title: 使用 Intune 部署 Teams 電話和 Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文提供 Microsoft Teams 顯示所支援之概觀和功能。
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120775"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="1ce28-103">使用 Intune 部署 Teams 電話和 Teams</span><span class="sxs-lookup"><span data-stu-id="1ce28-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="1ce28-104">本文提供如何使用 Intune 部署 Teams 電話和 Teams 顯示概觀。</span><span class="sxs-lookup"><span data-stu-id="1ce28-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="1ce28-105">條件式存取</span><span class="sxs-lookup"><span data-stu-id="1ce28-105">Conditional Access</span></span>

<span data-ttu-id="1ce28-106">條件式 Access 是 Azure Active Directory (Azure AD) 功能，可協助確保存取 Office 365 資源的裝置已妥善管理且安全。</span><span class="sxs-lookup"><span data-stu-id="1ce28-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="1ce28-107">如果您將條件式存取原則適用于 Teams 服務，Android 裝置 (包括 Teams 手機和 Teams) 會顯示存取 Teams 必須註冊至 Intune，其設定必須符合您的原則。</span><span class="sxs-lookup"><span data-stu-id="1ce28-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="1ce28-108">如果裝置未註冊到 Intune，或已註冊，但其設定不符合您的政策，條件式 Access 會防止使用者登錄或使用裝置上的 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ce28-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="1ce28-109">一般來說，Intune 中定義的合規性政策會指派給使用者群組。</span><span class="sxs-lookup"><span data-stu-id="1ce28-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="1ce28-110">這表示如果您指派 Android 合規性原則給 user@contoso.com，該原則會一併適用于 Android 智慧型手機，以及任何已 user@contoso.com Android 型的 Teams 裝置。</span><span class="sxs-lookup"><span data-stu-id="1ce28-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="1ce28-111">如果您使用條件式 Access，而需要強制執行 Intune 註冊，在貴組織中，您需要設定幾個專案，以順利註冊 Intune：</span><span class="sxs-lookup"><span data-stu-id="1ce28-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="1ce28-112">**Intune 授權** 使用者必須擁有 Intune 授權，以登錄 Teams 裝置。</span><span class="sxs-lookup"><span data-stu-id="1ce28-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="1ce28-113">只要 Teams 裝置已登錄具有有效 Intune 授權之使用者帳戶，該裝置就會在 Microsoft Intune 中自動註冊，做為登錄程式之一部分。</span><span class="sxs-lookup"><span data-stu-id="1ce28-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="1ce28-114">**設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="1ce28-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="1ce28-115">設定 Intune 以註冊 Teams Android 型裝置</span><span class="sxs-lookup"><span data-stu-id="1ce28-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="1ce28-116">Android 版 Teams 裝置在 Intune 中透過 Android 裝置系統管理員和 DA (管理) 管理。</span><span class="sxs-lookup"><span data-stu-id="1ce28-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="1ce28-117">在裝置可以註冊到 Intune 之前，有幾個基本步驟可以執行。</span><span class="sxs-lookup"><span data-stu-id="1ce28-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="1ce28-118">如果您目前已經使用 Intune 管理裝置，您可能已經完成所有上述工作。</span><span class="sxs-lookup"><span data-stu-id="1ce28-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="1ce28-119">如果沒有，請執行以下工作：</span><span class="sxs-lookup"><span data-stu-id="1ce28-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="1ce28-120">將 Intune MDM (行動裝置管理) 授權。</span><span class="sxs-lookup"><span data-stu-id="1ce28-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="1ce28-121">如果您之前從未使用過 Intune，您必須設定 MDM 授權，才能註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="1ce28-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="1ce28-122">詳細資訊，請參閱 [設定行動裝置管理機關](/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="1ce28-122">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="1ce28-123">這是建立新 Intune 租使用者時必須執行一次的步驟。</span><span class="sxs-lookup"><span data-stu-id="1ce28-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="1ce28-124">啟用 Android 裝置系統管理員註冊。</span><span class="sxs-lookup"><span data-stu-id="1ce28-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="1ce28-125">Android 型 Teams 裝置是使用 Intune 以裝置系統管理員裝置管理。</span><span class="sxs-lookup"><span data-stu-id="1ce28-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="1ce28-126">針對新建立租使用者，裝置系統管理員註冊預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="1ce28-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="1ce28-127">詳細資訊，請參閱 [Android 裝置系統管理員註冊](/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="1ce28-127">For more information, see [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="1ce28-128">指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="1ce28-128">Assign licenses to users.</span></span> <span data-ttu-id="1ce28-129">註冊至 Intune 的 Teams 裝置使用者必須獲得有效的 Intune 授權。</span><span class="sxs-lookup"><span data-stu-id="1ce28-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="1ce28-130">詳細資訊，請參閱 [指派授權給使用者，讓使用者可以在 Intune 中註冊裝置](/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="1ce28-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="1ce28-131">指派裝置系統管理員合規性政策。</span><span class="sxs-lookup"><span data-stu-id="1ce28-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="1ce28-132">建立 Android 裝置系統管理員合規性政策，並將其指派給包含要登錄 Teams 裝置之使用者的 Azure Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="1ce28-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="1ce28-133">詳細資訊，請參閱使用 [合規性原則來設定使用 Intune 管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="1ce28-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce28-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1ce28-134">See also</span></span>

[<span data-ttu-id="1ce28-135">Teams 的電話</span><span class="sxs-lookup"><span data-stu-id="1ce28-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="1ce28-136">Microsoft Teams 的 IP 電話認證</span><span class="sxs-lookup"><span data-stu-id="1ce28-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="1ce28-137">Teams 顯示</span><span class="sxs-lookup"><span data-stu-id="1ce28-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="1ce28-138">在 Teams 中管理裝置</span><span class="sxs-lookup"><span data-stu-id="1ce28-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="1ce28-139">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="1ce28-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)