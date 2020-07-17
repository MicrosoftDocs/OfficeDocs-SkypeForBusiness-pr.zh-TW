---
title: Lync 中使用者相片的顯示方式
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="95a48-102">Lync 中使用者相片的顯示方式</span><span class="sxs-lookup"><span data-stu-id="95a48-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a48-103">_**主題上次修改日期：** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="95a48-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="95a48-104">**摘要：** 顯示在 Lync 用戶端中的使用者相片可能會因您使用哪個 Lync 功能而異，例如會議或 IM 交談。</span><span class="sxs-lookup"><span data-stu-id="95a48-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="95a48-105">Lync 2010 引進的功能可加入具有 Lync 設定檔的相片，以顯示給其他 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="95a48-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="95a48-106">您也可以選擇是否要在 Lync 用戶端中為您的連絡人顯示照片。</span><span class="sxs-lookup"><span data-stu-id="95a48-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="95a48-107">在 Lync 2013 中，支援高解析度的相片的使用者。</span><span class="sxs-lookup"><span data-stu-id="95a48-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="95a48-108">本主題說明 Lync 用戶端如何取得及顯示使用者相片、儲存影像的位置、每個影像來源的限制，以及不同 Lync 服務使用使用者相片的方式。</span><span class="sxs-lookup"><span data-stu-id="95a48-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="95a48-109">規劃考量</span><span class="sxs-lookup"><span data-stu-id="95a48-109">Planning considerations</span></span>

<span data-ttu-id="95a48-110">當您規劃對使用者相片的支援時，應考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="95a48-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="95a48-111">高定義使用者相片支援要求使用者的信箱位於 Exchange 2013，而 Lync 使用者帳戶位於 Lync 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="95a48-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="95a48-112">只有在使用 Lync Server 2013 和 Exchange 2013 的環境中，才支援高定義使用者相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="95a48-113">信箱在 Exchange 2010 上的使用者，將永遠使用來自 AD DS 的**thumbnailPhoto**屬性做為使用者相片的來源。</span><span class="sxs-lookup"><span data-stu-id="95a48-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="95a48-114">從 AD DS 儲存為**thumbnailPhoto**屬性的使用者相片不會顯示在外部/同盟連絡人。</span><span class="sxs-lookup"><span data-stu-id="95a48-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="95a48-115">如果使用者連絡人的相片儲存在 AD DS 中，則所使用的圖像檔案限制為96×96圖元，且不得超過 100 KB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="95a48-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="95a48-116">如果 Lync Server 與 Exchange Server 之間的連線已遺失，將會顯示使用者的低解析度**thumbnailPhoto** ，並只會顯示給內部使用者。</span><span class="sxs-lookup"><span data-stu-id="95a48-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="95a48-117">當使用中的音箱未啟用影片時，會在 Lync 2013 會議中顯示高解析度的使用者相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="95a48-118">此外，將滑鼠移到圖庫中的縮圖照片上方，會顯示高解析度的相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="95a48-119">Lync 2010 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="95a48-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="95a48-120">在 Lync 2010 用戶端中，您可以從兩個選項中選擇顯示設定檔的相片、**預設的公司圖片**及**顯示網址中的圖片**。</span><span class="sxs-lookup"><span data-stu-id="95a48-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="95a48-121">預設公司圖片</span><span class="sxs-lookup"><span data-stu-id="95a48-121">Default corporate picture</span></span>

<span data-ttu-id="95a48-122">當您選擇 [**預設公司圖片**] 選項時，Lync 會從 Active Directory 網域服務中取得為您顯示的相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="95a48-123">使用的影像是定義為 Active Directory 網域服務中**thumbnailPhoto**屬性值的影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="95a48-124">這是 Exchange 在 Outlook 中顯示圖像時所使用的相同檔案。</span><span class="sxs-lookup"><span data-stu-id="95a48-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="95a48-125">使用 Active Directory 網域服務中的影像的考慮包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="95a48-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="95a48-126">只支援最高96圖元至96圖元的影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="95a48-127">影像的檔案大小限制為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="95a48-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="95a48-128">根據預設，使用者可以變更用於**thumbnailPhoto**屬性的影像，但不能直接透過 Lync 用戶端進行。</span><span class="sxs-lookup"><span data-stu-id="95a48-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="95a48-129">您可以透過 Active Directory 網域服務停用此。</span><span class="sxs-lookup"><span data-stu-id="95a48-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="95a48-130">儲存在 Active Directory 網域服務中的圖像不會顯示給組織外部的連絡人，即使他們是同盟連絡人也是一樣。</span><span class="sxs-lookup"><span data-stu-id="95a48-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="95a48-131">在大型組織中，儲存及檢索大量使用者的影像可能會影響 Active Directory 網域服務資料庫的大小和效能。</span><span class="sxs-lookup"><span data-stu-id="95a48-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="95a48-132">有限的影像尺寸及檔案大小表示只可使用低解析度圖像。</span><span class="sxs-lookup"><span data-stu-id="95a48-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="95a48-133">使用者如何在 Active Directory 網域服務中管理使用者相片</span><span class="sxs-lookup"><span data-stu-id="95a48-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="95a48-134">使用者無法直接透過 Lync 2010 用戶端變更其 Active Directory 網域服務設定檔中所使用的影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="95a48-135">他們可以使用下列其中一個選項來執行（如果有的話）：</span><span class="sxs-lookup"><span data-stu-id="95a48-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="95a48-136">**SharePoint 伺服器**    使用者可以將相片上傳至「我的網站」的 SharePoint 伺服器上，然後[在 SharePoint 中設定設定檔同步](https://go.microsoft.com/fwlink/p/?linkid=507466)處理，以同步處理相片至 Active Directory 網域服務中的**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="95a48-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="95a48-137">**儲存在可公開存取的 URL**     上的相片使用者可以設定其使用者相片，指定要使用之影像的公開存取 URL。</span><span class="sxs-lookup"><span data-stu-id="95a48-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="95a48-138">在沒有密碼的情況下，必須可公開存取影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="95a48-139">儲存在指定網址的圖像會透過狀態資訊中的連絡人卡片類別轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="95a48-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="95a48-140">當 Lync 用戶端需要顯示使用者相片時，它會從指定的網址檢索圖像。</span><span class="sxs-lookup"><span data-stu-id="95a48-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="95a48-141">**Windows PowerShell**     的 Exchange 2010 Cmdlet管理員可以在 Exchange 2010 管理命令介面中執行[Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) Cmdlet，以管理**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="95a48-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="95a48-142">當圖像匯入 Exchange 2010 Cmdlet 時，檔案大小限制為 10 KB。</span><span class="sxs-lookup"><span data-stu-id="95a48-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="95a48-143">**協力廠商工具**    使用者只能將自己的相片上傳至**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="95a48-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="95a48-144">顯示網址中的圖片</span><span class="sxs-lookup"><span data-stu-id="95a48-144">Show a picture from a web address</span></span>

<span data-ttu-id="95a48-145">當您選擇 [**顯示網址中的圖片**] 選項時，lync 會在您所輸入的位址取得影像，並在 Lync 中為您的使用者相片顯示此圖像。</span><span class="sxs-lookup"><span data-stu-id="95a48-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="95a48-146">使用網址中的圖像的考慮包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="95a48-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="95a48-147">檔案大小限制是由用戶端原則中使用[New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) Cmdlet 所定義的**MaxPhotoSizeKB**屬性所決定。</span><span class="sxs-lookup"><span data-stu-id="95a48-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="95a48-148">預設大小限制為 30 KB。</span><span class="sxs-lookup"><span data-stu-id="95a48-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="95a48-149">最大值為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="95a48-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="95a48-150">對影像的解析度沒有任何限制，但如果您嘗試使用超過大小限制的圖像檔案，則不會將其下載至 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="95a48-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="95a48-151">您可以將值設為0，以停用 Lync 中的所有使用者相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="95a48-152">來自網址的使用者相片可由外部同盟連絡人看到。</span><span class="sxs-lookup"><span data-stu-id="95a48-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="95a48-153">使用用戶端原則 Cmdlet 來管理使用者相片</span><span class="sxs-lookup"><span data-stu-id="95a48-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="95a48-154">在 Lync Server 2010 中，用戶端原則設定會以 CsClientPolicy Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="95a48-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="95a48-155">設定的原則設定會透過帶內布建來傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="95a48-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="95a48-156">CsClientPolicy Cmdlet 的兩個參數，可判斷使用者的照片體驗**DisplayPhoto**和**MaxPhotoSizeKB**。</span><span class="sxs-lookup"><span data-stu-id="95a48-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="95a48-157">對應**DisplayPhoto**和**MaxPhotoSizeKB**的內帶內布布建參數稱為**PhotoUsage**。</span><span class="sxs-lookup"><span data-stu-id="95a48-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="95a48-158">**PhotoUsage**參數的值會透過**endpointConfiguration** **provisionGroup**傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="95a48-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="95a48-159">如需詳細資訊，請參閱[用戶端原則和設定的概述](https://go.microsoft.com/fwlink/?linkid=507470)。</span><span class="sxs-lookup"><span data-stu-id="95a48-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="95a48-160">**DisplayPhoto**參數值會決定使用者相片影像的來源。</span><span class="sxs-lookup"><span data-stu-id="95a48-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="95a48-161">下表包含支援的值。</span><span class="sxs-lookup"><span data-stu-id="95a48-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95a48-162">DisplayPhoto 參數值</span><span class="sxs-lookup"><span data-stu-id="95a48-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="95a48-163">圖像來源</span><span class="sxs-lookup"><span data-stu-id="95a48-163">Image source</span></span></th>
<th><span data-ttu-id="95a48-164">Lync 2010 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="95a48-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95a48-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="95a48-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="95a48-166">無</span><span class="sxs-lookup"><span data-stu-id="95a48-166">none</span></span></p></td>
<td><p><span data-ttu-id="95a48-167"><strong>不要顯示我的圖片</strong></span><span class="sxs-lookup"><span data-stu-id="95a48-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a48-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="95a48-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="95a48-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="95a48-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="95a48-170"><strong>預設公司圖片</strong></span><span class="sxs-lookup"><span data-stu-id="95a48-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a48-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="95a48-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="95a48-172">網址</span><span class="sxs-lookup"><span data-stu-id="95a48-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="95a48-173"><strong>顯示網址中的圖片</strong></span><span class="sxs-lookup"><span data-stu-id="95a48-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="95a48-174">Lync 2010 用戶端如何取得相片</span><span class="sxs-lookup"><span data-stu-id="95a48-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="95a48-175">在 Lync 2010 中，使用者相片是透過通訊錄服務在伺服器上管理。</span><span class="sxs-lookup"><span data-stu-id="95a48-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="95a48-176">Lync 用戶端會先查詢伺服器上的通訊錄 Web 查詢（ABWQ）服務（透過通訊群組清單擴充 Web 服務公開），以取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="95a48-177">用戶端會接收圖像檔案，然後將它複製到使用者的快取，以避免每次需要顯示圖像時進行下載。</span><span class="sxs-lookup"><span data-stu-id="95a48-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="95a48-178">從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務專案中。</span><span class="sxs-lookup"><span data-stu-id="95a48-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="95a48-179">通訊錄服務每24小時就會刪除所有快取的影像，這表示在伺服器的快取中，新使用者影像的更新最多可能需要24小時。</span><span class="sxs-lookup"><span data-stu-id="95a48-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="95a48-180">您可以使用[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) Cmdlet 強制更新快取。</span><span class="sxs-lookup"><span data-stu-id="95a48-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="95a48-181">「目前狀態」中包含的使用者相片也有一個相關聯的雜湊值，Lync 用戶端使用該雜湊值來判斷是否有更新的影像可用。</span><span class="sxs-lookup"><span data-stu-id="95a48-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="95a48-182">用戶端會自動向顯示狀態中所用之圖像檔案的變更通知。</span><span class="sxs-lookup"><span data-stu-id="95a48-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="95a48-183">因為相片未儲存在 GalContacts 資料庫中，所以下載使用者相片不會依存于用戶端原則（<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>）中的 [ <STRONG>AddressBookAvailability</STRONG> ] 設定。</span><span class="sxs-lookup"><span data-stu-id="95a48-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="95a48-184">ABWQ 服務的查詢包含下列屬性：</span><span class="sxs-lookup"><span data-stu-id="95a48-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="95a48-185">**PhotoHash**    二進位照片資料的雜湊值，可用來判斷目前的相片是否已變更。</span><span class="sxs-lookup"><span data-stu-id="95a48-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="95a48-186">**PhotoRelPath**    儲存在伺服器上之圖像檔案的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="95a48-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="95a48-187">**PhotoSize**    圖像檔案的大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="95a48-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="95a48-188">**TimeStamp**    從伺服器上最後下載圖像檔案，並將其複製到用戶端快取的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="95a48-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="95a48-189">接下來，在檢索影像檔之後，Lync 2010 用戶端會將從查詢所傳回的屬性值與用戶端從頻帶所接收的屬性值進行比較，以查看兩者是否不同。</span><span class="sxs-lookup"><span data-stu-id="95a48-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="95a48-190">如果這些值不同，用戶端會使用 HTTP GET 要求來檢索已登入使用者的影像檔。</span><span class="sxs-lookup"><span data-stu-id="95a48-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="95a48-191">此外，用戶端會每隔24小時從該伺服器的快取版本所建立的時間，與用戶端上的值進行比較，以比較伺服器上的**PhotoHash**屬性值。</span><span class="sxs-lookup"><span data-stu-id="95a48-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="95a48-192">如果值不同，用戶端就會知道圖像檔已變更。</span><span class="sxs-lookup"><span data-stu-id="95a48-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="95a48-193">若要取得更新的映射檔，用戶端會重新查詢 ABWQ 服務，以使用伺服器上的映射檔更新用戶端快取中的映射檔，也就是在用戶端快取中重設檔上的**時間戳記**。</span><span class="sxs-lookup"><span data-stu-id="95a48-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="95a48-194">以下是對 ABWQ 服務的查詢回應範例：</span><span class="sxs-lookup"><span data-stu-id="95a48-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="95a48-195">Lync 2013 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="95a48-195">User photos in Lync 2013</span></span>

<span data-ttu-id="95a48-196">Lync 2013 為使用者相片引進高解析度影像的支援。</span><span class="sxs-lookup"><span data-stu-id="95a48-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="95a48-197">Lync 2013 也包含支援在 Exchange 2013 上的使用者信箱中儲存使用者相片，這會移除 Lync 2010 中所提供的影像解析度和大小限制。</span><span class="sxs-lookup"><span data-stu-id="95a48-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="95a48-198">Lync 2013 中的使用者相片可以是最高648圖元的648圖元，檔案大小最高為 20 MB。</span><span class="sxs-lookup"><span data-stu-id="95a48-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="95a48-199">Lync 2013 中的高解析度相片必須位於 Exchange 2013 的使用者信箱中，而且只支援 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="95a48-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="95a48-200">這種與 Exchange 的整合利用2013版本的 Lync、Exchange 及 SharePoint 稱為 Oauth 所包含的新授權架構。</span><span class="sxs-lookup"><span data-stu-id="95a48-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="95a48-201">如果部署中未使用 Exchange 2013，則對使用者相片的支援與 Lync 2010 相同。</span><span class="sxs-lookup"><span data-stu-id="95a48-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="95a48-202">不過，在 Lync 2013 用戶端中，選擇要使用的相片的使用者選項是不同的。</span><span class="sxs-lookup"><span data-stu-id="95a48-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="95a48-203">在 Lync 2013 用戶端中，使用者可以選擇 [**隱藏我的圖片**] 或 [**顯示我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="95a48-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="95a48-204">預設不提供**從網站顯示圖片**的選項，但可透過指派用戶端原則來啟用。</span><span class="sxs-lookup"><span data-stu-id="95a48-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="95a48-205">隱藏我的圖片</span><span class="sxs-lookup"><span data-stu-id="95a48-205">Hide my picture</span></span>

<span data-ttu-id="95a48-206">使用者相片的設定是在 Lync 2013 的 [**選項**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="95a48-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="95a48-207">當您選擇 [**隱藏我的圖片**] 時，不會在 lync 用戶端中為您顯示任何使用者相片，但您的相片仍會顯示在連絡人卡片上和 Lync 以外的地方。</span><span class="sxs-lookup"><span data-stu-id="95a48-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="95a48-208">顯示我的圖片</span><span class="sxs-lookup"><span data-stu-id="95a48-208">Show my picture</span></span>

<span data-ttu-id="95a48-209">當您選擇 [**顯示我的圖片**] 選項時，您的使用者相片會顯示在您的 lync 用戶端，以及 lync 交談中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="95a48-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="95a48-210">使用的圖像是儲存在 AD DS 中的圖像。</span><span class="sxs-lookup"><span data-stu-id="95a48-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="95a48-211">顯示網站中的圖片</span><span class="sxs-lookup"><span data-stu-id="95a48-211">Show a picture from a website</span></span>

<span data-ttu-id="95a48-212">在設定了用戶端原則加以啟用之後，Lync 2013 中的 [**顯示來自網站的圖片**] 選項便可供使用。</span><span class="sxs-lookup"><span data-stu-id="95a48-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="95a48-213">用戶端版本必須比15.0.4535.1002 （隨[Lync 累積更新安裝）：2013年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)更新。</span><span class="sxs-lookup"><span data-stu-id="95a48-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="95a48-214">使用者可能需要登出後再重新登入，以查看用戶端中的變更。</span><span class="sxs-lookup"><span data-stu-id="95a48-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="95a48-215">您可以在 Lync Server 管理命令介面中執行[Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則，將用戶端原則設定為啟用**從網站設定來顯示圖片**。</span><span class="sxs-lookup"><span data-stu-id="95a48-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="95a48-216">下列 Cmdlet 範例會示範如何針對您部署中的所有使用者，全域設定原則：</span><span class="sxs-lookup"><span data-stu-id="95a48-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="95a48-217">當圖像上傳至使用者的信箱時，Exchange 會自動建立可用於用戶端應用程式的較低解析度版本的影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="95a48-218">使用者相片也會在 AD DS 中更新。</span><span class="sxs-lookup"><span data-stu-id="95a48-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="95a48-219">在 AD DS 中更新映射檔時，會在 AD DS 中為 thumbnailPhoto 建立並使用 48 x 48 圖元影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="95a48-220">任何現有的圖像都會取代。</span><span class="sxs-lookup"><span data-stu-id="95a48-220">Any existing image is replaced.</span></span> <span data-ttu-id="95a48-221">因此，如果您已將 96 x 96 圖像新增至 AD DS，它會以新的 48 x 48 影像覆寫。</span><span class="sxs-lookup"><span data-stu-id="95a48-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="95a48-222">這只是重要的一點，就是您在環境中使用 Lync 2010 用戶端，因為這些用戶端會從 AD DS 取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="95a48-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="95a48-223">如果您的組織中有 Lync 2010 用戶端，您可以匯入 96 x 96 圖元影像以取代 AD DS 所建立的影像。</span><span class="sxs-lookup"><span data-stu-id="95a48-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="95a48-224">Lync 2013 中的使用者相片支援</span><span class="sxs-lookup"><span data-stu-id="95a48-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="95a48-225">在 Lync 2013 中，使用者照片支援三種影像解析度，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="95a48-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="95a48-226">所使用的映射是由指派給 Lync 使用者的用戶端原則設定所決定。</span><span class="sxs-lookup"><span data-stu-id="95a48-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="95a48-227">如需詳細資訊，請參閱本主題中的「管理使用者的相片使用用戶端原則 Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="95a48-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95a48-228">圖像解析度（圖元）</span><span class="sxs-lookup"><span data-stu-id="95a48-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="95a48-229">應用程式</span><span class="sxs-lookup"><span data-stu-id="95a48-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95a48-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="95a48-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="95a48-231">如果沒有選取更高的解析度影像，則使用</span><span class="sxs-lookup"><span data-stu-id="95a48-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a48-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="95a48-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="95a48-233">在 Outlook Web App 和 Outlook 2013 中使用</span><span class="sxs-lookup"><span data-stu-id="95a48-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a48-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="95a48-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="95a48-235">在 Lync 2013 桌面用戶端和 Lync 2013 Web App 中使用</span><span class="sxs-lookup"><span data-stu-id="95a48-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95a48-236">任何在 Exchange 2013 中啟用信箱的使用者，都可以透過 Outlook Web Access 或 Lync 2013 用戶端選項上傳不同的影像，包括高解析度照片。</span><span class="sxs-lookup"><span data-stu-id="95a48-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="95a48-237">使用的影像建議設定包括：</span><span class="sxs-lookup"><span data-stu-id="95a48-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="95a48-238">**影像解析度**    648 x 648 圖元</span><span class="sxs-lookup"><span data-stu-id="95a48-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="95a48-239">**色彩深度**    24位</span><span class="sxs-lookup"><span data-stu-id="95a48-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="95a48-240">**圖像檔案大小**    最多 20 MB</span><span class="sxs-lookup"><span data-stu-id="95a48-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="95a48-241">**檔案格式**    Jpeg</span><span class="sxs-lookup"><span data-stu-id="95a48-241">**File format**   JPEG</span></span>

<span data-ttu-id="95a48-242">典型的24位 JPEG 圖像（648圖元 x 648 圖元）的檔案大小約為大約 240 KB，所以每四個使用者相片都需要 1 MB 的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="95a48-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

