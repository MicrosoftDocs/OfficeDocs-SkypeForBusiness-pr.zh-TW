---
title: 部署團隊使用 Intune 顯示手機和團隊
ms.author: v-lanac
author: lanachin
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
description: 本文提供 Microsoft 團隊顯示所支援的功能和功能的概覽。
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787616"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="7561b-103">部署團隊使用 Intune 顯示手機和團隊</span><span class="sxs-lookup"><span data-stu-id="7561b-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="7561b-104">本文將簡要說明如何使用 Intune 部署團隊手機和團隊。</span><span class="sxs-lookup"><span data-stu-id="7561b-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="7561b-105">條件式存取</span><span class="sxs-lookup"><span data-stu-id="7561b-105">Conditional Access</span></span>

<span data-ttu-id="7561b-106">條件式存取是 Azure Active Directory (的 Azure AD) 功能，可協助您確保能正確管理存取 Office 365 資源的裝置，且安全。</span><span class="sxs-lookup"><span data-stu-id="7561b-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="7561b-107">如果您將條件式存取原則套用至團隊服務，Android 裝置 (包括 [團隊電話] 和 [團隊]，會顯示需要將其登錄至 Intune 且其設定必須符合您原則的) 。</span><span class="sxs-lookup"><span data-stu-id="7561b-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="7561b-108">如果裝置未登錄至 Intune，或已註冊，但其設定不符合您的原則，條件式存取將會防止使用者登入或使用裝置上的 [小組] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7561b-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="7561b-109">通常，在 Intune 中定義的規範原則會指派給使用者群組。</span><span class="sxs-lookup"><span data-stu-id="7561b-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="7561b-110">這表示如果您指派 Android 規範原則至 user@contoso.com，該原則會同等地套用到他們的 Android 智慧型手機，以及 user@contoso.com 登入的任何 Android 版的小組裝置。</span><span class="sxs-lookup"><span data-stu-id="7561b-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="7561b-111">如果您使用條件式存取（需要強制進行 Intune 註冊），在您的組織中，您需要設定幾個專案，才能允許成功進行 Intune 登記：</span><span class="sxs-lookup"><span data-stu-id="7561b-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="7561b-112">**Intune 授權** 登入小組裝置的使用者必須具備 Intune 的授權。</span><span class="sxs-lookup"><span data-stu-id="7561b-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="7561b-113">只要團隊裝置登入擁有有效 Intune 授權的使用者帳戶，裝置就會自動在登入程式中登入 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="7561b-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="7561b-114">**設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確設定的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7561b-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="7561b-115">將 Intune 設定為以 Android 版為基礎的裝置註冊團隊</span><span class="sxs-lookup"><span data-stu-id="7561b-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="7561b-116">在 Intune 中，以 Android 裝置管理員身分管理的團隊是由 android 裝置管理員 (DA) 管理。</span><span class="sxs-lookup"><span data-stu-id="7561b-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="7561b-117">在能將裝置登記到 Intune 之前，請先執行幾個基本步驟。</span><span class="sxs-lookup"><span data-stu-id="7561b-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="7561b-118">如果您目前已使用 Intune 管理裝置，您可能已經完成所有這些專案。</span><span class="sxs-lookup"><span data-stu-id="7561b-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="7561b-119">如果沒有，以下是要執行的動作：</span><span class="sxs-lookup"><span data-stu-id="7561b-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="7561b-120">將 Intune MDM (行動裝置管理) 頒發機構設定。</span><span class="sxs-lookup"><span data-stu-id="7561b-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="7561b-121">如果您之前從未使用過 Intune，您必須先設定 MDM 頒發機構，才能註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7561b-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="7561b-122">如需詳細資訊，請參閱 [設定行動裝置管理機構](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="7561b-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="7561b-123">此為一次性步驟，必須在建立新的 Intune 租使用者完成。</span><span class="sxs-lookup"><span data-stu-id="7561b-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="7561b-124">啟用 Android 裝置管理員註冊。</span><span class="sxs-lookup"><span data-stu-id="7561b-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="7561b-125">Android 版的團隊裝置是使用 Intune 作為裝置系統管理員裝置進行管理。</span><span class="sxs-lookup"><span data-stu-id="7561b-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="7561b-126">新建立的租使用者預設會關閉 [裝置管理員註冊]。</span><span class="sxs-lookup"><span data-stu-id="7561b-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="7561b-127">如需詳細資訊，請參閱 [Android 裝置系統管理員註冊](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="7561b-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="7561b-128">指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="7561b-128">Assign licenses to users.</span></span> <span data-ttu-id="7561b-129">必須為團隊裝置使用者註冊到 Intune 的使用者指派有效的 Intune 授權。</span><span class="sxs-lookup"><span data-stu-id="7561b-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="7561b-130">如需詳細資訊，請參閱 [指派授權給使用者，讓他們可以在 Intune 中註冊裝置](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="7561b-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="7561b-131">指派裝置管理員合規性原則。</span><span class="sxs-lookup"><span data-stu-id="7561b-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="7561b-132">建立 Android 裝置管理員合規性原則，並將它指派給 Azure Active Directory 群組，該群組包含要登入小組裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="7561b-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="7561b-133">如需詳細資訊，請參閱 [使用合規性策略來設定您使用 Intune 管理的裝置規則](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="7561b-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="7561b-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7561b-134">See also</span></span>

[<span data-ttu-id="7561b-135">Teams 的電話</span><span class="sxs-lookup"><span data-stu-id="7561b-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="7561b-136">Microsoft 團隊的 IP 手機認證</span><span class="sxs-lookup"><span data-stu-id="7561b-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="7561b-137">團隊顯示</span><span class="sxs-lookup"><span data-stu-id="7561b-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="7561b-138">在 Teams 中管理裝置</span><span class="sxs-lookup"><span data-stu-id="7561b-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="7561b-139">團隊 Marketplace</span><span class="sxs-lookup"><span data-stu-id="7561b-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
