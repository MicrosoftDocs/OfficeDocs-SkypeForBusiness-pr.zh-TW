---
title: Microsoft Teams 原則控制概覽
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 原則控制的概覽。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed0e5aa3a39147238bf0ade57df509a31f0f13e8
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142809"
---
# <a name="policy-control-overview-for-microsoft-teams"></a><span data-ttu-id="55858-103">Microsoft Teams 原則控制概覽</span><span class="sxs-lookup"><span data-stu-id="55858-103">Policy control overview for Microsoft Teams</span></span>

<span data-ttu-id="55858-104">Microsoft 致力於為您提供所需的資訊和控制，以便您在使用 Microsoft Teams (Microsoft 365 的一部分) 時對收集和使用資料的方式做出選擇。</span><span class="sxs-lookup"><span data-stu-id="55858-104">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Teams, a part of Microsoft 365.</span></span>

<span data-ttu-id="55858-105">本文旨在提供以下區域隱私權控制的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="55858-105">This article is intended to provide you with information about privacy controls for the following areas:</span></span>

- <span data-ttu-id="55858-106">收集並傳送給 Microsoft 的 **診斷資料**，其中包含您的組織中執行 Windows 的電腦上所使用 Teams 和 Office 軟體的資料。</span><span class="sxs-lookup"><span data-stu-id="55858-106">**Diagnostic data** that is collected and sent to Microsoft about Teams and Office software being used on computers running Windows in your organization.</span></span>
- <span data-ttu-id="55858-107">**[連線體驗]**：使用以雲端為基礎的功能來為您和您的使用者提供增強的 Teams 和 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="55858-107">**Connected experiences** that use cloud-based functionality to provide enhanced Teams and Office features to you and your users.</span></span>

<span data-ttu-id="55858-108">這些變更的其中一個部分，是提供新的及更新的使用者介面 (UI) 元素和原則設定。</span><span class="sxs-lookup"><span data-stu-id="55858-108">As part of these changes, there are new and updated user interface (UI) elements and policy settings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55858-109">如需進一步閱讀，請檢視 [Microsoft 365 Apps 企業版隱私權控制概觀](/deployoffice/privacy/overview-privacy-controls)。</span><span class="sxs-lookup"><span data-stu-id="55858-109">For further reading, please review [Overview of privacy controls for Microsoft 365 Apps for enterprise](/deployoffice/privacy/overview-privacy-controls).</span></span>

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a><span data-ttu-id="55858-110">從 Microsoft 365 Apps 企業版傳送到 Microsoft 的診斷資料</span><span class="sxs-lookup"><span data-stu-id="55858-110">Diagnostic data sent from Microsoft 365 Apps for enterprise to Microsoft</span></span>

<span data-ttu-id="55858-111">診斷資料的用途：</span><span class="sxs-lookup"><span data-stu-id="55858-111">Diagnostic data is used to:</span></span>

- <span data-ttu-id="55858-112">保持 Teams 的安全和最新狀態。</span><span class="sxs-lookup"><span data-stu-id="55858-112">Keep Teams secure and up-to-date.</span></span>
- <span data-ttu-id="55858-113">偵測、診斷和修復問題。</span><span class="sxs-lookup"><span data-stu-id="55858-113">Detect, diagnose, and remediate problems.</span></span>
- <span data-ttu-id="55858-114">改善產品。</span><span class="sxs-lookup"><span data-stu-id="55858-114">Make product improvements.</span></span>

<span data-ttu-id="55858-115">其中一些收集的資料範例包括：</span><span class="sxs-lookup"><span data-stu-id="55858-115">An example of some of the collected data includes:</span></span>

- <span data-ttu-id="55858-116">應用程式語言</span><span class="sxs-lookup"><span data-stu-id="55858-116">Application language</span></span>
- <span data-ttu-id="55858-117">使用者類型</span><span class="sxs-lookup"><span data-stu-id="55858-117">User type</span></span>
- <span data-ttu-id="55858-118">OS 的組建版本</span><span class="sxs-lookup"><span data-stu-id="55858-118">Build version of the OS</span></span>

## <a name="clients-that-adhere-to-diagnostic-controls"></a><span data-ttu-id="55858-119">遵循診斷控制的用戶端</span><span class="sxs-lookup"><span data-stu-id="55858-119">Clients that adhere to diagnostic controls</span></span>

<span data-ttu-id="55858-120">下列用戶端遵循診斷控制，並將提交資料：</span><span class="sxs-lookup"><span data-stu-id="55858-120">The following clients adhere to diagnostic controls and will submit data:</span></span>

- <span data-ttu-id="55858-121">iOS</span><span class="sxs-lookup"><span data-stu-id="55858-121">iOS</span></span>
- <span data-ttu-id="55858-122">Android</span><span class="sxs-lookup"><span data-stu-id="55858-122">Android</span></span>
- <span data-ttu-id="55858-123">桌上型電腦 (僅限使用 win32 API 的元件)</span><span class="sxs-lookup"><span data-stu-id="55858-123">Desktop (only the component that is using the win32 API)</span></span>

<span data-ttu-id="55858-124">若要查看必要診斷資料事件及其屬性的清單，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="55858-124">To see a list of required diagnostic data events and their properties, see the following articles:</span></span>

- [<span data-ttu-id="55858-125">Microsoft Teams 的行動裝置必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="55858-125">Required mobile diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-mobile.md)
- [<span data-ttu-id="55858-126">Microsoft Teams 的桌面必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="55858-126">Required desktop diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a><span data-ttu-id="55858-127">從 Teams 應用程式傳送到 Microsoft 的診斷資料</span><span class="sxs-lookup"><span data-stu-id="55858-127">Diagnostic data sent from the Teams app to Microsoft</span></span>

<span data-ttu-id="55858-128">系統會收集此診斷資料並傳送給 Microsoft，其中包含您的組織中執行 Windows 的電腦上所使用的 Teams 軟體的資料。</span><span class="sxs-lookup"><span data-stu-id="55858-128">This diagnostic data is collected and sent to Microsoft about Teams software being used on computers running Windows in your organization.</span></span>

<span data-ttu-id="55858-129">Teams 軟體有三個層級的診斷資料可供選擇：</span><span class="sxs-lookup"><span data-stu-id="55858-129">There are three levels of diagnostic data for Teams software that you can choose from:</span></span>

- <span data-ttu-id="55858-130">**必要**：最基本的資料，以保持 Office 的安全、最新狀態且在安裝它的裝置上如預期地運作。</span><span class="sxs-lookup"><span data-stu-id="55858-130">**Required** The minimum data necessary to help keep Office secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>
- <span data-ttu-id="55858-131">**選用**：額外的資料，可協助我們改善產品，並提供增強的資料來協助我們偵測、診斷和修復問題。</span><span class="sxs-lookup"><span data-stu-id="55858-131">**Optional** Additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and remediate issues.</span></span>
- <span data-ttu-id="55858-132">**無**：不收集也不傳送給我們任何使用者裝置上執行的 Teams 軟體的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="55858-132">**Neither** No diagnostic data about Teams software running on the user’s device is collected and sent to us.</span></span> <span data-ttu-id="55858-133">不過，這個選項會大幅限制我們偵測、診斷以及修復您的使用者使用 Teams 時可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="55858-133">This option, however, significantly limits our ability to detect, diagnose, and remediate problems your users may encounter using Teams.</span></span>

<span data-ttu-id="55858-134">必要的診斷資料可能包括：例如用戶端在裝置上所安裝的 Teams 版本的相關資料，或包括指出 Teams 應用程式在嘗試加入會議時當機的資料。</span><span class="sxs-lookup"><span data-stu-id="55858-134">Required diagnostic data could include, for example, information about the version of Teams client installed on the device, or include information that indicates that the Teams application is crashing when trying to join a meeting.</span></span> <span data-ttu-id="55858-135">選用的診斷資料可能包括：開始撥打電話所耗費的時間，這可能代表連線能力和網路效能方面的問題。</span><span class="sxs-lookup"><span data-stu-id="55858-135">Optional diagnostic data could include information about the time it takes to initiate a phone call, which could indicate an issue with connectivity or network performance.</span></span>

<span data-ttu-id="55858-136">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="55858-136">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="55858-137">身為組織的系統管理員，您可以使用原則設定來選擇要傳送給我們的診斷資料層級。</span><span class="sxs-lookup"><span data-stu-id="55858-137">As an admin for your organization, you’ll be able to use a policy setting to choose which level of diagnostic data is sent to us.</span></span> <span data-ttu-id="55858-138">除非您變更設定，否則會將選用的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="55858-138">Optional diagnostic data will be sent to Microsoft unless you change the setting.</span></span> <span data-ttu-id="55858-139">提供選用的診斷資料有助於 Microsoft 的 Office 工程團隊偵測、診斷以及減輕問題，以降低對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="55858-139">Providing optional diagnostic data better enables the Office engineering team at Microsoft to detect, diagnose, and mitigate issues to reduce impacts to your organization.</span></span> 

<span data-ttu-id="55858-140">若要選擇要傳送給我們的診斷資料層級，請使用 [Office 雲端原則服務](/deployoffice/overview-office-cloud-policy-service)，並設定 *設定 Office 傳送給 Microsoft 的用戶端軟體診斷資料層級* 原則設定。</span><span class="sxs-lookup"><span data-stu-id="55858-140">To choose which level of diagnostic data is sent to us, use the [Office cloud policy service](/deployoffice/overview-office-cloud-policy-service) and configure the *Configure the level of client software diagnostic data sent by Office to Microsoft* policy setting.</span></span> <span data-ttu-id="55858-141">這是用來設定 Microsoft 365 Apps 企業版中其他 Office 應用程式 (例如 Word、Excel 和 PowerPoint) 所傳送診斷資料層級的相同原則設定。</span><span class="sxs-lookup"><span data-stu-id="55858-141">This is the same policy setting that is used to configure which level of diagnostic data is sent by other Office apps (such as Word, Excel, and PowerPoint) that come with Microsoft 365 Apps for enterprise.</span></span>

<span data-ttu-id="55858-142">如果使用者是使用其組織的認證 (有時稱為公司或學校帳戶) 登入 Office，使用者將無法為他們的裝置變更診斷資料層級。</span><span class="sxs-lookup"><span data-stu-id="55858-142">Your users won’t be able to change the diagnostic data level for their devices if they are signed in to Teams with their organizational credentials, which is sometimes referred to as a work or school account.</span></span>

<span data-ttu-id="55858-143">此診斷資料不包含使用者名稱、其電子郵件地址或其他使用者內容，例如 Teams 中共用的 Office 檔案、在 Teams 中發送的聊天訊息，或在 Teams 頻道中發佈之文章的文字。</span><span class="sxs-lookup"><span data-stu-id="55858-143">This diagnostic data doesn’t include names of users, their email addresses, or other user content, such as Office files shared in Teams, a chat message sent in Teams, or the text of a post published in a Teams channel.</span></span> <span data-ttu-id="55858-144">我們的系統會建立一個唯一的識別碼，該識別碼會與使用者的診斷資料建立關聯。</span><span class="sxs-lookup"><span data-stu-id="55858-144">Our system creates a unique ID that it associates with your user’s diagnostic data.</span></span> <span data-ttu-id="55858-145">當我們收到的診斷資料顯示我們的 Teams 應用程式當機了 100 次，這個唯一識別碼可讓我們判斷是單一使用者當機了 100 次，還是 100 個不同的使用者各當機一次。</span><span class="sxs-lookup"><span data-stu-id="55858-145">When we receive diagnostic data showing that the Teams app crashed 100 times, this unique ID lets us determine if it was a single user who crashed 100 times or if it was 100 different users who each crashed once.</span></span> <span data-ttu-id="55858-146">我們不會使用此唯一識別碼來識別出特定使用者。</span><span class="sxs-lookup"><span data-stu-id="55858-146">We don’t use this unique ID to identify a specific user.</span></span>

<span data-ttu-id="55858-147">若要查看傳送給 Microsoft 的是哪些診斷資料，您可以使用診斷資料檢視器，您可以自 Microsoft Store 免費下載並安裝該工具。</span><span class="sxs-lookup"><span data-stu-id="55858-147">To see what diagnostic data is being sent to Microsoft, you can use the Diagnostic Data Viewer, which you can download and install for free from the Microsoft Store.</span></span> <span data-ttu-id="55858-148">如需詳細資訊，請參閱[使用 Office 的診斷資料檢視器](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)。</span><span class="sxs-lookup"><span data-stu-id="55858-148">For more information, see [Using the Diagnostic Data Viewer with Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).</span></span>

> [!NOTE]
> <span data-ttu-id="55858-149">針對診斷資料檢視器的支援，可在執行 Android 裝置的 Teams 上取得。</span><span class="sxs-lookup"><span data-stu-id="55858-149">Support for the Diagnostic Data Viewer is available for Teams on devices running Android.</span></span> <span data-ttu-id="55858-150">針對執行 Windows、macOS 或 iOS 裝置上的 Teams 支援正在處理中。</span><span class="sxs-lookup"><span data-stu-id="55858-150">Support for Teams on devices running Windows, macOS, or iOS is being worked on.</span></span>

## <a name="required-service-data-for-connected-experiences"></a><span data-ttu-id="55858-151">連線體驗的必要服務資料</span><span class="sxs-lookup"><span data-stu-id="55858-151">Required service data for connected experiences</span></span>

<span data-ttu-id="55858-152">必要的服務資料是使我們能夠提供這些雲端型連線體驗並協助保護體驗的安全及讓其如預期執行的資料。</span><span class="sxs-lookup"><span data-stu-id="55858-152">Required service data is data that enables us to deliver these cloud-based connected experiences and help make these experiences secure and perform as expected.</span></span> <span data-ttu-id="55858-153">您可以選擇不提供這項功能給您的使用者，在這種情況下，此資料就不會提供給 Microsoft 來支援連線體驗的功能。</span><span class="sxs-lookup"><span data-stu-id="55858-153">You can choose to not offer this functionality to your users, in which case this information will not be provided to Microsoft to support the functionality of connected experiences.</span></span> <span data-ttu-id="55858-154">您可以深入瞭解 [必要服務資料](/deployoffice/privacy/required-service-data)。</span><span class="sxs-lookup"><span data-stu-id="55858-154">You can learn more about [required service data](/deployoffice/privacy/required-service-data).</span></span>

## <a name="essential-services-for-microsoft-teams"></a><span data-ttu-id="55858-155">Microsoft Teams 的基本服務</span><span class="sxs-lookup"><span data-stu-id="55858-155">Essential services for Microsoft Teams</span></span>

<span data-ttu-id="55858-156">也有一組服務是 Microsoft 365 Apps 企業版運作的基礎，因此不能加以停用。</span><span class="sxs-lookup"><span data-stu-id="55858-156">There is also a set of services that are essential to how Microsoft 365 Apps for enterprise functions and cannot be disabled.</span></span> <span data-ttu-id="55858-157">例如，可確認您取得使用 Microsoft 365 Apps 企業版正確授權的授權服務。</span><span class="sxs-lookup"><span data-stu-id="55858-157">For example, the licensing service that confirms that you are properly licensed to use Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="55858-158">無論您設定了哪些其他原則設定，都會收集有關這些服務的必要服務資料並將其傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="55858-158">Required service data about these services is collected and sent to Microsoft, regardless of any other policy settings that you have configured.</span></span>

<span data-ttu-id="55858-159">如需詳細資訊，請參閱 [Office 的基本服務](/deployoffice/privacy/essential-services)。</span><span class="sxs-lookup"><span data-stu-id="55858-159">For more information, see [Essential services for Office](/deployoffice/privacy/essential-services).</span></span>