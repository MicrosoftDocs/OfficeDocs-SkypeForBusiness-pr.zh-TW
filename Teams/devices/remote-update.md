---
title: 遠端Microsoft Teams更新裝置
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
description: 使用 Microsoft Teams管理中心Teams遠端更新手機、Teams面板和共同Teams橫條圖
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347884"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="1ae23-103">遠端Microsoft Teams更新裝置</span><span class="sxs-lookup"><span data-stu-id="1ae23-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="1ae23-104">您可以使用 Microsoft Teams 系統管理中心，遠端更新 Teams 裝置，例如 Teams 手機、Teams 面板和共同合作橫條圖，您也可以選擇裝置固件自動更新行為。</span><span class="sxs-lookup"><span data-stu-id="1ae23-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="1ae23-105">您可以使用系統管理中心在裝置上更新Teams：</span><span class="sxs-lookup"><span data-stu-id="1ae23-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="1ae23-106">Teams應用程式與團隊系統管理員</span><span class="sxs-lookup"><span data-stu-id="1ae23-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="1ae23-107">公司入口網站應用程式</span><span class="sxs-lookup"><span data-stu-id="1ae23-107">Company portal app</span></span>
- <span data-ttu-id="1ae23-108">OEM 代理應用程式</span><span class="sxs-lookup"><span data-stu-id="1ae23-108">OEM agent app</span></span>
- <span data-ttu-id="1ae23-109">裝置固件</span><span class="sxs-lookup"><span data-stu-id="1ae23-109">Device firmware</span></span>

<span data-ttu-id="1ae23-110">裝置固件更新可以自動或排程為未來的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1ae23-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="1ae23-111">其他可用的裝置更新不會自動申請，但可以手動或排程未來日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1ae23-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae23-112">雖然可以排程裝置固件更新，但如果排定的日期和時間落在所配置的最長 30 天或 90 天延遲之後，則當達到最大延遲時間時，即會採用固件更新。</span><span class="sxs-lookup"><span data-stu-id="1ae23-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="1ae23-113">排程的日期和時間會被忽略。</span><span class="sxs-lookup"><span data-stu-id="1ae23-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="1ae23-114">此外，遠端Microsoft Teams裝置是美國政府雲端租使用者 (GCC-High) 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="1ae23-115">若要管理裝置，您必須是全域系統管理員、Teams系統管理員，或Teams系統管理員。有關系統管理員角色的資訊，請參閱使用 Microsoft Teams[系統管理員角色來管理Teams。](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1ae23-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="1ae23-116">選擇自動裝置固件更新行為</span><span class="sxs-lookup"><span data-stu-id="1ae23-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="1ae23-117">裝置固件更新會自動使用。</span><span class="sxs-lookup"><span data-stu-id="1ae23-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="1ae23-118">您可以選擇是否要在更新發行後 (于更新發行) 後的第一個週末或更新發行後的 30 或 90 天內，于第一個週末申請更新。</span><span class="sxs-lookup"><span data-stu-id="1ae23-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="1ae23-119">根據預設，裝置固件更新會于一次發行後 30 天內使用。</span><span class="sxs-lookup"><span data-stu-id="1ae23-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae23-120">您的裝置上不會Teams更新版本。</span><span class="sxs-lookup"><span data-stu-id="1ae23-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="1ae23-121">相反地，您裝置上自動申請的更新會延遲一個版本。</span><span class="sxs-lookup"><span data-stu-id="1ae23-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="1ae23-122">例如，假設您的裝置已採用版本"10"，且版本"11"已發行。</span><span class="sxs-lookup"><span data-stu-id="1ae23-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="1ae23-123">版本 "11" 尚未適用。</span><span class="sxs-lookup"><span data-stu-id="1ae23-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="1ae23-124">相反地，您的裝置只會在版本 「12」 發行後更新為版本「11」。</span><span class="sxs-lookup"><span data-stu-id="1ae23-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae23-125">某些裝置還不支援自動固件更新。</span><span class="sxs-lookup"><span data-stu-id="1ae23-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="1ae23-126">在不支援自動更新的裝置上，將自動固件更新設定適用于這些裝置並沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="1ae23-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="1ae23-127">如需您的裝置是否支援自動固件更新的問題，請與您的裝置製造商聯繫。</span><span class="sxs-lookup"><span data-stu-id="1ae23-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="1ae23-128">若要為裝置選擇自動更新行為，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ae23-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="1ae23-129">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="1ae23-130">流覽 **裝置**  >  **IP 電話** 或 **共同Teams\*\*\*\*面板**。</span><span class="sxs-lookup"><span data-stu-id="1ae23-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="1ae23-131">選取一或多個裝置， **然後選取** 更新 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="1ae23-132">在 **固件自動更新下**，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1ae23-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="1ae23-133">**一旦可用** 第二個最新裝置固件更新會于最新更新發行後的第一個週末進行。</span><span class="sxs-lookup"><span data-stu-id="1ae23-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="1ae23-134">**延後 30 天** 第二個最新裝置固件更新會于最新更新發行後的 30 天內使用。</span><span class="sxs-lookup"><span data-stu-id="1ae23-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="1ae23-135">**延後 90 天** 第二個最新裝置固件更新會于最新更新發行後的 90 天內使用。</span><span class="sxs-lookup"><span data-stu-id="1ae23-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="1ae23-136">選取 **更新**。</span><span class="sxs-lookup"><span data-stu-id="1ae23-136">Select **Update**.</span></span>

<span data-ttu-id="1ae23-137">如果基於任何原因，您需要還原裝置固件更新，您必須將裝置重設為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="1ae23-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="1ae23-138">使用裝置製造商的指示重設裝置。</span><span class="sxs-lookup"><span data-stu-id="1ae23-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="1ae23-139">手動更新遠端裝置</span><span class="sxs-lookup"><span data-stu-id="1ae23-139">Manually update remote devices</span></span>

<span data-ttu-id="1ae23-140">當您使用系統管理中心更新一或多個裝置時，您可以決定是否立即更新裝置，或為未來的日期和時間排程更新。</span><span class="sxs-lookup"><span data-stu-id="1ae23-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="1ae23-141">若要手動更新遠端裝置，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ae23-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="1ae23-142">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="1ae23-143">流覽 **裝置**  >  **IP 電話** 或 **共同Teams\*\*\*\*面板**。</span><span class="sxs-lookup"><span data-stu-id="1ae23-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="1ae23-144">選取一或多個裝置， **然後選取** 更新 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="1ae23-145">如果您想要 **為** 未來的日期和時間排程更新，請選取在手動更新下排程。</span><span class="sxs-lookup"><span data-stu-id="1ae23-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="1ae23-146">更新會以時區中選取的時區日期和時間 **來申請**。</span><span class="sxs-lookup"><span data-stu-id="1ae23-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="1ae23-147">您所看到的內容取決於您已選取一或多個裝置。</span><span class="sxs-lookup"><span data-stu-id="1ae23-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="1ae23-148">下方的左影像顯示已選取多個裝置，而右側影像則顯示已選取的單一裝置。</span><span class="sxs-lookup"><span data-stu-id="1ae23-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置視圖":::

<span data-ttu-id="1ae23-150">當您選取多個裝置時，您可以選擇要適用于每個所選裝置的更新類型。</span><span class="sxs-lookup"><span data-stu-id="1ae23-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="1ae23-151">選取要申請的更新類型， **然後選取** 更新 。</span><span class="sxs-lookup"><span data-stu-id="1ae23-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="1ae23-152">當您選取單一裝置時，會顯示適用于該裝置的更新。</span><span class="sxs-lookup"><span data-stu-id="1ae23-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="1ae23-153">如果裝置可以使用多種更新類型，請選取要申請的每一種更新類型。</span><span class="sxs-lookup"><span data-stu-id="1ae23-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="1ae23-154">您可以查看裝置 **上** 所適用之目前版本， **以及將會申請** 的新版本。</span><span class="sxs-lookup"><span data-stu-id="1ae23-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="1ae23-155">選取要 (更新) ，然後選取 **更新**。</span><span class="sxs-lookup"><span data-stu-id="1ae23-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="1ae23-156">選取更新 **之後**，更新會在您選取的日期和時間，在您排程更新時，將更新應用程式至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="1ae23-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="1ae23-157">如果您沒有選取未來的日期和時間，更新會于幾分鐘內適用于您的裝置。</span><span class="sxs-lookup"><span data-stu-id="1ae23-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
