---
title: 使用 intune Teams手機Teams顯示
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
description: 本文提供螢幕顯示功能Microsoft Teams概觀。
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420818"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="cb61b-103">使用 intune Teams手機Teams顯示</span><span class="sxs-lookup"><span data-stu-id="cb61b-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="cb61b-104">本文提供如何部署概觀。</span><span class="sxs-lookup"><span data-stu-id="cb61b-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="cb61b-105">Teams Intune Teams手機和手機。</span><span class="sxs-lookup"><span data-stu-id="cb61b-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="cb61b-106">條件式存取</span><span class="sxs-lookup"><span data-stu-id="cb61b-106">Conditional Access</span></span>

<span data-ttu-id="cb61b-107">條件式 Access Azure Active Directory (Azure AD) 功能，可協助確保存取您Office 365資源的裝置獲得妥善管理且安全。</span><span class="sxs-lookup"><span data-stu-id="cb61b-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="cb61b-108">如果您將條件式存取原則適用于 Teams 服務，Android 裝置 (包括 Teams 手機和 Teams 會顯示) ，表示需要將 Teams 註冊到 Intune，且其設定必須符合您的原則。</span><span class="sxs-lookup"><span data-stu-id="cb61b-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="cb61b-109">如果裝置未註冊到 Intune，或已註冊，但其設定不符合您的政策，條件式 Access 會防止使用者登錄或使用裝置上的 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb61b-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="cb61b-110">一般來說，Intune 中定義的合規性政策會指派給使用者群組。</span><span class="sxs-lookup"><span data-stu-id="cb61b-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="cb61b-111">這表示如果您將 Android 合規性原則指派給 user@contoso.com，該原則會同樣適用于 Android 智慧型手機，以及任何已Teams Android user@contoso.com 裝置。</span><span class="sxs-lookup"><span data-stu-id="cb61b-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="cb61b-112">如果您使用條件式 Access，而需要強制執行 Intune 註冊，在貴組織中，您需要設定幾個專案，以順利註冊 Intune：</span><span class="sxs-lookup"><span data-stu-id="cb61b-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="cb61b-113">**Intune 授權** 使用者必須擁有 intune Teams裝置授權。</span><span class="sxs-lookup"><span data-stu-id="cb61b-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="cb61b-114">只要Teams已登錄具有有效 Intune 授權之使用者帳戶，裝置就會在 Microsoft Intune 中自動註冊為登錄程式。</span><span class="sxs-lookup"><span data-stu-id="cb61b-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="cb61b-115">**設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="cb61b-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="cb61b-116">設定 Intune 以註冊Teams Android 型裝置</span><span class="sxs-lookup"><span data-stu-id="cb61b-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="cb61b-117">TeamsAndroid 型裝置是由 Intune 透過 Android 裝置系統管理員 (DA) 管理。</span><span class="sxs-lookup"><span data-stu-id="cb61b-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="cb61b-118">在裝置可以註冊到 Intune 之前，有幾個基本步驟可以執行。</span><span class="sxs-lookup"><span data-stu-id="cb61b-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="cb61b-119">如果您目前已經使用 Intune 管理裝置，您可能已經完成所有這些工作。</span><span class="sxs-lookup"><span data-stu-id="cb61b-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="cb61b-120">如果沒有，請執行以下工作：</span><span class="sxs-lookup"><span data-stu-id="cb61b-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="cb61b-121">如果租使用者系統管理員想要將常見的地區電話註冊到 Intune，他們需要在帳戶新增 Intune 授權，並遵循 Intune 註冊的步驟。</span><span class="sxs-lookup"><span data-stu-id="cb61b-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="cb61b-122">如果用來登錄帳戶的使用者帳戶Teams Intune 沒有授權，必須停用該帳戶的 Intune 合規性策略和註冊限制。</span><span class="sxs-lookup"><span data-stu-id="cb61b-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="cb61b-123">將 Intune MDM (行動裝置管理) 授權。</span><span class="sxs-lookup"><span data-stu-id="cb61b-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="cb61b-124">如果您之前從未使用過 Intune，您必須設定 MDM 授權，才能註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cb61b-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="cb61b-125">詳細資訊，請參閱 [設定行動裝置管理機關](/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="cb61b-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="cb61b-126">這是建立新 Intune 租使用者時必須執行一次的步驟。</span><span class="sxs-lookup"><span data-stu-id="cb61b-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="cb61b-127">啟用 Android 裝置系統管理員註冊。</span><span class="sxs-lookup"><span data-stu-id="cb61b-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="cb61b-128">Android 型Teams裝置會以 Intune 的裝置系統管理員裝置管理。</span><span class="sxs-lookup"><span data-stu-id="cb61b-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="cb61b-129">根據預設，新建立租使用者會關閉裝置系統管理員註冊。</span><span class="sxs-lookup"><span data-stu-id="cb61b-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="cb61b-130">請參閱 [Android 裝置系統管理員註冊](/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="cb61b-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="cb61b-131">指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="cb61b-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="cb61b-132">註冊Teams Intune 的裝置使用者必須獲得有效的 Intune 授權。</span><span class="sxs-lookup"><span data-stu-id="cb61b-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="cb61b-133">詳細資訊，請參閱 [指派授權給使用者，讓使用者可以在 Intune 中註冊裝置](/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="cb61b-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="cb61b-134">指派裝置系統管理員合規性政策。</span><span class="sxs-lookup"><span data-stu-id="cb61b-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="cb61b-135">a.</span><span class="sxs-lookup"><span data-stu-id="cb61b-135">a.</span></span> <span data-ttu-id="cb61b-136">建立 Android 裝置系統管理員合規性政策。</span><span class="sxs-lookup"><span data-stu-id="cb61b-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="cb61b-137">b.</span><span class="sxs-lookup"><span data-stu-id="cb61b-137">b.</span></span> <span data-ttu-id="cb61b-138">將其指派給Azure Active Directory組，其中包含將登錄至Teams的使用者。</span><span class="sxs-lookup"><span data-stu-id="cb61b-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="cb61b-139">請參閱 [使用合規性原則來設定使用 Intune 管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="cb61b-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb61b-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cb61b-140">See also</span></span>

[<span data-ttu-id="cb61b-141">Teams 的電話</span><span class="sxs-lookup"><span data-stu-id="cb61b-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="cb61b-142">IP 電話已Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb61b-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="cb61b-143">Teams顯示</span><span class="sxs-lookup"><span data-stu-id="cb61b-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="cb61b-144">在 Teams 中管理裝置</span><span class="sxs-lookup"><span data-stu-id="cb61b-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="cb61b-145">Teams市場</span><span class="sxs-lookup"><span data-stu-id="cb61b-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)