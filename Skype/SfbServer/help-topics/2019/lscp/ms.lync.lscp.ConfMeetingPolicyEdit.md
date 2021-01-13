---
title: 會議原則建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: 會議原則定義使用者在會議 (又稱為會議) 時可用的功能和功能。
ms.openlocfilehash: 97b022771f0077239475137496c222748b6ef828
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824883"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="04bb0-103">會議原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="04bb0-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="04bb0-104">會議原則定義使用者在會議 (又稱為會議) 時可用的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="04bb0-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="04bb0-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="04bb0-105">UI Reference</span></span>

<span data-ttu-id="04bb0-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="04bb0-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="04bb0-107">**範圍** 識別您要建立或修改之會議原則的範圍：全域、網站或使用者。</span><span class="sxs-lookup"><span data-stu-id="04bb0-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="04bb0-108">**名稱** 每個會議原則都需要一個名稱。</span><span class="sxs-lookup"><span data-stu-id="04bb0-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="04bb0-109">通用和網站會議原則的命名方式是預設的，而且名稱無法變更。</span><span class="sxs-lookup"><span data-stu-id="04bb0-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="04bb0-110">針對使用者會議原則，請使用識別使用者或使用者群組的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="04bb0-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04bb0-111">在您儲存會議原則之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="04bb0-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="04bb0-112">**描述** 此欄位是選用的。</span><span class="sxs-lookup"><span data-stu-id="04bb0-112">**Description** This field is optional.</span></span> <span data-ttu-id="04bb0-113">使用它來提供會議原則的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="04bb0-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="04bb0-114">**召集人原則** 本節中的設定適用于組織會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="04bb0-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="04bb0-115">如果選取了設定，使用者就可以組織具有指定之特性的會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="04bb0-116">若未選取設定，使用者就無法使用此特性組織會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="04bb0-117">這些設定不會決定使用者可以以其他會議中的參與者的身分存取權。</span><span class="sxs-lookup"><span data-stu-id="04bb0-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="04bb0-118">按一下標籤旁的向上箭號或向下箭頭，以關閉或開啟區段。</span><span class="sxs-lookup"><span data-stu-id="04bb0-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="04bb0-119">**會議大小上限** 允許會議的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="04bb0-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="04bb0-120">根據預設，會議大小上限為250。</span><span class="sxs-lookup"><span data-stu-id="04bb0-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="04bb0-121">**允許參與者邀請匿名使用者** 選取此核取方塊可允許使用者邀請匿名使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="04bb0-122">匿名使用者是指不具備組織之 Active Directory 網域服務之認證的使用者，因此未進行驗證。</span><span class="sxs-lookup"><span data-stu-id="04bb0-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="04bb0-123">**錄製** 指定參與者是否可以記錄會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="04bb0-124">選項為 [ **無** ] 或 [ **啟用錄製**]。</span><span class="sxs-lookup"><span data-stu-id="04bb0-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="04bb0-125">**允許同盟和匿名參與者進行記錄** 選取此核取方塊可允許外部和未經驗證的參與者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="04bb0-126">**音訊/視頻** 指定參與者是否可以使用音訊和影片：</span><span class="sxs-lookup"><span data-stu-id="04bb0-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="04bb0-127">**無** 選取此選項可防止使用音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="04bb0-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="04bb0-128">**啟用 IP 音訊** 選取這個選項，允許使用音訊，但不允許影片。</span><span class="sxs-lookup"><span data-stu-id="04bb0-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="04bb0-129">**啟用 IP 音訊/影片** 選取此選項可同時允許音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="04bb0-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="04bb0-130">**啟用 PSTN 電話撥入式會議** 如果您在 [ **音訊/影片**] 中啟用音訊，請選取此核取方塊以允許使用者使用公用交換電話網路 (PSTN) ，撥打會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="04bb0-131">**允許匿名參與者撥出** 如果您允許使用者撥入會議，而您想要允許未驗證 (匿名) 使用者使用撥出 phoning 加入會議，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04bb0-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="04bb0-132">透過撥出 phoning，會議服務器呼叫使用者，而使用者接聽電話以加入會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="04bb0-133">**允許未啟用 Enterprise Voice 的參與者撥出** 如果您在 [ **音訊/影片**] 中啟用音訊，請選取此核取方塊，可允許未啟用 Enterprise Voice 的使用者加入使用撥出 phoning 的會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="04bb0-134">使用撥出 phoning 時，會議服務器會電話給使用者，然後使用者接聽電話以加入會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="04bb0-135">**允許多個影片流量** 如果您在 [ **音訊/影片**] 中啟用 [影片]，請選取此核取方塊以允許使用者利用圖庫 View 影片來組織會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="04bb0-136">當選中此核取方塊時，此設定可讓使用者組織傳送多個影片資料流程的會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="04bb0-137">未選取此核取方塊時，使用者只能組織傳送單一影片的會議。</span><span class="sxs-lookup"><span data-stu-id="04bb0-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04bb0-138">此選項會決定會議所支援的影片資料流程類型。</span><span class="sxs-lookup"><span data-stu-id="04bb0-138">This option determines the type of video stream supported by the conference.</span></span> <span data-ttu-id="04bb0-139">它不會判斷參與者是否可以接收多個影片。</span><span class="sxs-lookup"><span data-stu-id="04bb0-139">It does not determine whether participants can receive multiple video streams.</span></span> <span data-ttu-id="04bb0-140">[ **允許參與者加入多個影片資料流程** ] 選項會決定參與者是否可以接收多個影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="04bb0-140">The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="04bb0-141">**資料** 共同作業指定會議是否允許資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="04bb0-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="04bb0-142">選項為 **無** 或 **啟用資料** 共同作業。</span><span class="sxs-lookup"><span data-stu-id="04bb0-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="04bb0-143">下列設定適用于資料共同作業：</span><span class="sxs-lookup"><span data-stu-id="04bb0-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="04bb0-144">**允許同盟和匿名參與者下載內容** 如果允許資料共同作業，選取此核取方塊可允許外部和未經驗證的使用者從會議下載投影片或講義等內容。</span><span class="sxs-lookup"><span data-stu-id="04bb0-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="04bb0-145">**允許參與者傳輸** 檔案如果允許資料共同作業，選取此核取方塊可允許在會議期間傳送檔給所有參與者。</span><span class="sxs-lookup"><span data-stu-id="04bb0-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="04bb0-146">**啟用批註** 如果允許資料共同作業，選取此核取方塊可允許參與者在會議期間共用的內容上，進行螢幕上的批註。</span><span class="sxs-lookup"><span data-stu-id="04bb0-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="04bb0-147">**啟用 PowerPoint 標注** 如果您允許批註，選取此核取方塊可允許參與者在會議期間共用 PowerPoint 幻燈片中的批註。</span><span class="sxs-lookup"><span data-stu-id="04bb0-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="04bb0-148">**啟用輪詢** 如果允許資料共同作業，選取此核取方塊可允許參與者在會議期間舉行投票。</span><span class="sxs-lookup"><span data-stu-id="04bb0-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="04bb0-149">**應用程式共用** 指定會議是否允許應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="04bb0-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="04bb0-150">選項為 [ **停用應用程式共用** ] 或 [ **啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="04bb0-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="04bb0-151">應用程式共用適用下列設定：</span><span class="sxs-lookup"><span data-stu-id="04bb0-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="04bb0-152">**允許參與者取得控制權** 如果允許應用程式共用，選取此核取方塊可允許參與者控制在會議期間共用的應用程式或桌面。</span><span class="sxs-lookup"><span data-stu-id="04bb0-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="04bb0-153">**允許同盟和匿名參與者取得控制權** 如果允許應用程式共用，選取此核取方塊可允許外部和未經驗證的參與者控制在會議期間共用的應用程式或桌面。</span><span class="sxs-lookup"><span data-stu-id="04bb0-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="04bb0-154">**參與者原則** 本節中的設定適用于會議或兩方會話中的參與者的使用者。</span><span class="sxs-lookup"><span data-stu-id="04bb0-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="04bb0-155">由於下列設定是個別使用者的設定，所以會議或兩方會話中的一位使用者，在同一部會議或兩方會話中的功能可能會與其他使用者的功能不同。</span><span class="sxs-lookup"><span data-stu-id="04bb0-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="04bb0-156">按一下標籤旁的向上箭號或向下箭頭，以關閉或開啟區段。</span><span class="sxs-lookup"><span data-stu-id="04bb0-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="04bb0-157">選取 [ **啟用應用程式和桌面共用** ]，以允許使用者在參與會議或兩方會話時共用應用程式或其桌面。</span><span class="sxs-lookup"><span data-stu-id="04bb0-157">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session.</span></span> <span data-ttu-id="04bb0-158">選取 [ **停用應用程式和桌面共用** ]，可防止使用者在參與會議或兩方會話時共用應用程式或其桌面。</span><span class="sxs-lookup"><span data-stu-id="04bb0-158">Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="04bb0-159">**啟用對等檔案傳輸** 選取此核取方塊可允許人員對個人的檔案傳輸 (也就是說，在會議或兩方會話期間，不會涉及所有參與者的檔案傳輸) 。</span><span class="sxs-lookup"><span data-stu-id="04bb0-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="04bb0-160">**啟用對等錄製** 選取此核取方塊可允許使用者錄製兩方的會話。</span><span class="sxs-lookup"><span data-stu-id="04bb0-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="04bb0-161">**讓參與者加入多個影片資料流程** 選取此核取方塊可允許參與者在允許的會議中接收圖庫 View 影片。</span><span class="sxs-lookup"><span data-stu-id="04bb0-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="04bb0-162">如果未選取此選項，參與者只能接收單一影片，不論會議允許的功能為何。</span><span class="sxs-lookup"><span data-stu-id="04bb0-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04bb0-163">[ **允許多個影片資料流程** ] 決定會議是否允許多個影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="04bb0-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="04bb0-164">如需會議功能及功能的詳細資訊，請參閱規劃檔中的 [會議綜述](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="04bb0-164">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="04bb0-165">如需使用會議原則的詳細資訊，請參閱 Operations 檔中的 [會議原則](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="04bb0-165">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


