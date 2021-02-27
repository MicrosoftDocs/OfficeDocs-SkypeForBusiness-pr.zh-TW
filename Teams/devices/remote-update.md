---
title: 遠端更新 Microsoft Teams 裝置
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用 Teams 系統管理中心遠端更新 Microsoft Teams 手機、Teams 面板和共同合作長條
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347884"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="f8479-103">遠端更新 Microsoft Teams 裝置</span><span class="sxs-lookup"><span data-stu-id="f8479-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="f8479-104">使用 Microsoft Teams 系統管理中心，您可以遠端更新 Teams 裝置，例如 Teams 手機、Teams 面板和共同合作長條，而且您可以選擇裝置內款的自動更新行為。</span><span class="sxs-lookup"><span data-stu-id="f8479-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="f8479-105">您可以使用 Teams 系統管理中心在裝置上更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="f8479-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="f8479-106">Teams 應用程式與 Teams 系統管理員代理程式</span><span class="sxs-lookup"><span data-stu-id="f8479-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="f8479-107">公司入口網站應用程式</span><span class="sxs-lookup"><span data-stu-id="f8479-107">Company portal app</span></span>
- <span data-ttu-id="f8479-108">OEM 代理程式應用程式</span><span class="sxs-lookup"><span data-stu-id="f8479-108">OEM agent app</span></span>
- <span data-ttu-id="f8479-109">裝置中</span><span class="sxs-lookup"><span data-stu-id="f8479-109">Device firmware</span></span>

<span data-ttu-id="f8479-110">裝置方程式可以自動進行更新，也可以排程為未來的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f8479-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="f8479-111">其他可用的裝置更新不會自動適用，但可以手動或排程于未來的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f8479-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="f8479-112">雖然可以排程裝置中的更新，但如果排定的日期和時間落在所配置的最長 30 天或 90 天延遲之後，當達到最大延遲時，即會使用該更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="f8479-113">排程的日期和時間會被忽略。</span><span class="sxs-lookup"><span data-stu-id="f8479-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="f8479-114">此外，遠端更新 Microsoft Teams 裝置是美國政府雲端租使用者 (GCC-High) 。</span><span class="sxs-lookup"><span data-stu-id="f8479-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="f8479-115">若要管理裝置，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。有關系統管理員角色的資訊，請參閱使用[Microsoft Teams 系統管理員角色來管理 Teams。](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f8479-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="f8479-116">選擇自動裝置新訊更新行為</span><span class="sxs-lookup"><span data-stu-id="f8479-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="f8479-117">裝置中會自動使用裝置中的更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="f8479-118">您可以選擇是否要在更新發行後 (于更新發行後的第一個週末或更新發行後的 30 或 90 天，于) 或 30 天之後，再使用更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="f8479-119">根據預設，裝置方程式會更新 30 天，一次發行。</span><span class="sxs-lookup"><span data-stu-id="f8479-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8479-120">Teams 裝置上不會使用最新的新版更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="f8479-121">相反地，自動在裝置上所使用更新會延後一個版本。</span><span class="sxs-lookup"><span data-stu-id="f8479-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="f8479-122">例如，假設您的裝置已使用版本"10"，且已發行版本本 "11"。</span><span class="sxs-lookup"><span data-stu-id="f8479-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="f8479-123">版本 "11" 尚未適用。</span><span class="sxs-lookup"><span data-stu-id="f8479-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="f8479-124">相反地，您的裝置只會在版本 "12" 發行後更新為版本 "11"。</span><span class="sxs-lookup"><span data-stu-id="f8479-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="f8479-125">部分裝置目前不支援自動更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="f8479-126">在不支援自動更新的裝置上，將自動更新設定適用于這些裝置並沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="f8479-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="f8479-127">如需裝置是否支援自動更新的相關問題，請與您的裝置製造商聯繫。</span><span class="sxs-lookup"><span data-stu-id="f8479-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="f8479-128">若要選擇您裝置自動更新的行為，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f8479-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="f8479-129">請流覽以前往 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="f8479-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="f8479-130">流覽 **裝置**  >  **IP 電話、\*\*\*\*共同合作長條** 或 **Teams 面板**。</span><span class="sxs-lookup"><span data-stu-id="f8479-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="f8479-131">選取一或多個裝置， **然後選取更新**。</span><span class="sxs-lookup"><span data-stu-id="f8479-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="f8479-132">在 **Firmware 自動更新下**，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f8479-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="f8479-133">**一旦可用** 最新更新發行後的第一個週末，即會使用第二個最新的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="f8479-134">**延後 30 天** 第二個最新裝置新訊的更新會于最新更新發行後的 30 天內執行。</span><span class="sxs-lookup"><span data-stu-id="f8479-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="f8479-135">**延後 90 天** 第二個最新裝置新訊的更新會于最新更新發行後的 90 天內執行。</span><span class="sxs-lookup"><span data-stu-id="f8479-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="f8479-136">選取 **更新**。</span><span class="sxs-lookup"><span data-stu-id="f8479-136">Select **Update**.</span></span>

<span data-ttu-id="f8479-137">如果基於任何原因，您需要還原裝置方程式更新，您必須將裝置重設為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="f8479-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="f8479-138">使用裝置製造商的指示重設裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="f8479-139">手動更新遠端裝置</span><span class="sxs-lookup"><span data-stu-id="f8479-139">Manually update remote devices</span></span>

<span data-ttu-id="f8479-140">當您使用系統管理中心更新一或多個裝置時，您可以決定是否要立即更新裝置，或排定未來日期和時間的更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="f8479-141">若要手動更新遠端裝置，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f8479-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="f8479-142">請流覽以前往 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="f8479-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="f8479-143">流覽 **裝置**  >  **IP 電話、\*\*\*\*共同合作長條** 或 **Teams 面板**。</span><span class="sxs-lookup"><span data-stu-id="f8479-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="f8479-144">選取一或多個裝置， **然後選取更新**。</span><span class="sxs-lookup"><span data-stu-id="f8479-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="f8479-145">如果您要 **將更新\*\*\*\*排程** 為未來的日期和時間，請在手動更新下選取排程。</span><span class="sxs-lookup"><span data-stu-id="f8479-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="f8479-146">更新會于時區中所選時區的 **日期和時間進行。**</span><span class="sxs-lookup"><span data-stu-id="f8479-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="f8479-147">您所看到的內容取決於您已選取一或多個裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="f8479-148">下圖左側顯示已選取多個裝置，而右邊的影像顯示已選取的單一裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置視圖":::

<span data-ttu-id="f8479-150">當您選取多個裝置時，您可以選擇要適用于每個所選裝置的更新類型。</span><span class="sxs-lookup"><span data-stu-id="f8479-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="f8479-151">選取要申請的更新類型， **然後選取更新**。</span><span class="sxs-lookup"><span data-stu-id="f8479-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="f8479-152">當您選取單一裝置時，會顯示裝置可用的更新。</span><span class="sxs-lookup"><span data-stu-id="f8479-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="f8479-153">如果裝置有多個更新類型可用，請選取要申請的每一種更新類型。</span><span class="sxs-lookup"><span data-stu-id="f8479-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="f8479-154">您可以查看裝置 **上** 所適用之目前版本，以及要 **申請的** 新版本。</span><span class="sxs-lookup"><span data-stu-id="f8479-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="f8479-155">選取要 () 的更新， **然後選取更新**。</span><span class="sxs-lookup"><span data-stu-id="f8479-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="f8479-156">選取更新 **之後**，若您已排程更新，更新會在您選取的日期與時間，將更新適用于您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="f8479-157">如果您未選取未來的日期和時間，更新會于幾分鐘內適用于您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f8479-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
