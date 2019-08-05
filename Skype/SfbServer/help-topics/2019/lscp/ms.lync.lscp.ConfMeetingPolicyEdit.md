---
title: 會議原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: 會議原則定義使用者可以在會議中使用的特色與功能。
ms.openlocfilehash: 137802662241c4348f65ddb33e96d59a6c42a286
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193208"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="37971-103">會議原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="37971-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="37971-104">會議原則定義使用者可以在會議中使用的特色與功能。</span><span class="sxs-lookup"><span data-stu-id="37971-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="37971-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="37971-105">UI Reference</span></span>

<span data-ttu-id="37971-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="37971-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="37971-107">**範圍**識別您要建立或修改的會議原則範圍: [全域]、[網站] 或 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="37971-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="37971-108">**名稱**每個會議原則都需要名稱。</span><span class="sxs-lookup"><span data-stu-id="37971-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="37971-109">全域和網站會議原則預設會命名, 且無法變更名稱。</span><span class="sxs-lookup"><span data-stu-id="37971-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="37971-110">針對使用者會議原則, 請使用識別使用者或使用者群組的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="37971-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37971-111">會議原則儲存完畢後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="37971-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="37971-112">**描述**此為選用欄位。</span><span class="sxs-lookup"><span data-stu-id="37971-112">**Description** This field is optional.</span></span> <span data-ttu-id="37971-113">使用它來提供會議原則的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="37971-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="37971-114">**召集人原則**此區段中的設定適用于組織會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="37971-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="37971-115">如果已選取設定, 使用者就可以組織具有指定特徵的會議。</span><span class="sxs-lookup"><span data-stu-id="37971-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="37971-116">如果未選取某個設定, 使用者就無法使用此特性組織會議。</span><span class="sxs-lookup"><span data-stu-id="37971-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="37971-117">這些設定不會判斷使用者在其他會議中要以參與者身分存取的專案。</span><span class="sxs-lookup"><span data-stu-id="37971-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="37971-118">按一下標籤旁的向上箭頭或向下箭頭關閉或開啟區段。</span><span class="sxs-lookup"><span data-stu-id="37971-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="37971-119">[**最大會議大小**]: 允許會議的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="37971-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="37971-120">最大會議大小預設為 250。</span><span class="sxs-lookup"><span data-stu-id="37971-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="37971-121">**允許參與者邀請匿名使用者**選取此核取方塊可讓使用者邀請匿名使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="37971-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="37971-122">匿名使用者是在貴組織的 Active Directory 網域服務中沒有認證的使用者, 因此沒有經過驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="37971-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="37971-123">**錄製**指定參與者是否可以錄製會議。</span><span class="sxs-lookup"><span data-stu-id="37971-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="37971-124">選項為 [**無**] 或 [**啟用錄製**]。</span><span class="sxs-lookup"><span data-stu-id="37971-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="37971-125">**允許聯盟和匿名參與者錄製**選取此核取方塊可允許外部與未驗證的參與者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="37971-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="37971-126">**音訊/視頻**指定參與者是否可以使用音訊和影片:</span><span class="sxs-lookup"><span data-stu-id="37971-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="37971-127">**None**選取此選項可避免使用音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="37971-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="37971-128">**啟用 IP 音訊**選取這個選項, 即可使用音訊, 但不允許影片。</span><span class="sxs-lookup"><span data-stu-id="37971-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="37971-129">**啟用 IP 音訊/視頻**選取此選項可允許音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="37971-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="37971-130">**啟用 PSTN 電話撥入式會議**如果您在**音訊/視頻**中啟用音訊, 請選取此核取方塊, 以允許使用者使用公開的交換電話網絡 (PSTN) 撥入會議。</span><span class="sxs-lookup"><span data-stu-id="37971-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="37971-131">**允許匿名參與者撥出**如果您允許使用者撥入會議, 而您想要允許未經驗證 (匿名) 使用者使用 [撥出 phoning] 加入會議, 請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="37971-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="37971-132">使用撥出 phoning, 會議服務器就會呼叫使用者, 而使用者會接聽電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="37971-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="37971-133">**允許未啟用企業語音的參與者撥出**如果您在**音訊/視頻**中啟用音訊, 請選取此核取方塊, 以允許未啟用企業語音的使用者使用撥出 phoning 來加入會議。</span><span class="sxs-lookup"><span data-stu-id="37971-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="37971-134">在撥出 phoning 中, 會議服務器會打電話給使用者, 然後使用者接聽電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="37971-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="37971-135">**允許多個視頻串流**如果您已啟用**音訊/影片**中的影片, 請選取此核取方塊, 以允許使用者使用圖庫 View 影片整理會議。</span><span class="sxs-lookup"><span data-stu-id="37971-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="37971-136">選取此核取方塊時, 此設定可讓使用者組織傳送多個影片串流的會議。</span><span class="sxs-lookup"><span data-stu-id="37971-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="37971-137">如果未選取此核取方塊, 使用者就只能組織傳送單一影片串流的會議。</span><span class="sxs-lookup"><span data-stu-id="37971-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37971-p110">此選項可決定會議支援的視訊資料流類型，但是無法決定參與者是否可以接收多個視訊資料流。[啟用參與者加入多個視訊資料流]\*\*\*\* 選項決定參與者是否可以接收多個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="37971-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="37971-141">**資料**共同作業指定會議是否允許資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="37971-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="37971-142">選項為 [**無**] 或 [**啟用資料**共同作業]。</span><span class="sxs-lookup"><span data-stu-id="37971-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="37971-143">資料共同作業具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="37971-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="37971-144">**允許聯盟和匿名參與者下載內容**如果您允許資料共同作業, 請選取此核取方塊, 以允許外部與未驗證的使用者從會議下載內容, 例如投影片或講義。</span><span class="sxs-lookup"><span data-stu-id="37971-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="37971-145">**允許參與者傳送**檔案如果您允許資料共同作業, 請選取此核取方塊, 以允許在會議期間傳送給所有參與者。</span><span class="sxs-lookup"><span data-stu-id="37971-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="37971-146">**啟用批註**如果您允許資料共同作業, 請選取此核取方塊, 以允許參與者在會議期間共用的內容上進行螢幕上的批註。</span><span class="sxs-lookup"><span data-stu-id="37971-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="37971-147">**啟用 PowerPoint 注釋**如果您允許 [批註], 請選取此核取方塊, 以允許參與者在會議期間共用的 PowerPoint 投影片中加上批註。</span><span class="sxs-lookup"><span data-stu-id="37971-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="37971-148">**啟用投票**如果您允許資料共同作業, 請選取此核取方塊, 以允許參與者在會議期間召開投票。</span><span class="sxs-lookup"><span data-stu-id="37971-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="37971-149">**應用程式共用**指定會議是否允許共用應用程式。</span><span class="sxs-lookup"><span data-stu-id="37971-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="37971-150">選項為 [**停用應用程式共用**] 或 [**啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="37971-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="37971-151">應用程式共用具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="37971-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="37971-152">**允許參與者取得控制權**如果您允許應用程式共用, 請選取此核取方塊, 以允許參與者控制在會議期間共用的應用程式或桌面。</span><span class="sxs-lookup"><span data-stu-id="37971-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="37971-153">**允許聯盟和匿名參與者取得控制權**如果您允許應用程式共用, 請選取此核取方塊, 以允許外部與未經驗證的參與者控制在會議期間共用的應用程式或桌面。</span><span class="sxs-lookup"><span data-stu-id="37971-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="37971-154">**參與者原則**此區段中的設定適用于在會議或二方會話中作為參與者的使用者。</span><span class="sxs-lookup"><span data-stu-id="37971-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="37971-155">因為下列設定是每個使用者的設定, 所以會議或兩方會話中的一位使用者的功能可能與相同會議或兩方會話中的另一個使用者具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="37971-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="37971-156">按一下標籤旁的向上箭頭或向下箭頭關閉或開啟區段。</span><span class="sxs-lookup"><span data-stu-id="37971-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="37971-p114">選取 [啟用應用程式和桌面共用]\*\*\*\* 可允許使用者在參與會議或兩名成員工作階段時，共用應用程式或其桌面。選取 [停用應用程式和桌面共用]\*\*\*\* 可防止使用者在參與會議或兩名成員工作階段時，共用應用程式或其桌面。</span><span class="sxs-lookup"><span data-stu-id="37971-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="37971-159">**啟用對等檔案傳輸**選取此核取方塊, 即可允許在會議或二方會話期間進行個人對個人的檔案傳輸 (也就是不涉及所有參與者的檔案傳輸)。</span><span class="sxs-lookup"><span data-stu-id="37971-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="37971-160">**啟用對等錄製**選取此核取方塊可讓使用者記錄兩方的會議。</span><span class="sxs-lookup"><span data-stu-id="37971-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="37971-161">**讓參與者加入多個視頻串流**選取此核取方塊可允許參與者在允許的會議中接收圖庫視圖影片。</span><span class="sxs-lookup"><span data-stu-id="37971-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="37971-162">如果未選取此選項, 參與者只能接收單一的視頻資料流程, 不論會議允許的內容為何。</span><span class="sxs-lookup"><span data-stu-id="37971-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37971-163">[允許多個視訊資料流]\*\*\*\* 決定會議是否允許多個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="37971-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="37971-p116">如需會議特性及功能的詳細資訊，請參閱規劃文件中的〈[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)〉。如需使用會議原則的詳細資訊，請參閱作業文件中的〈[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="37971-p116">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


