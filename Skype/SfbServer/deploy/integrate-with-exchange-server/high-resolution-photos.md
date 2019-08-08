---
title: 在商務用 Skype Server 中設定高解析度相片的使用方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '摘要: 在 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 中設定高解析度相片的使用。'
ms.openlocfilehash: 8d68cb75a053d7eb165383154514ca6ff8d1a941
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244321"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="57dff-103">在商務用 Skype Server 中設定高解析度相片的使用方式</span><span class="sxs-lookup"><span data-stu-id="57dff-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="57dff-104">**摘要:** 在 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 中設定高解析度相片的使用。</span><span class="sxs-lookup"><span data-stu-id="57dff-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="57dff-105">在商務用 Skype Server 相片中, 您可以儲存在使用者的 Exchange Server 2016 或 Exchange Server 2013 信箱中, 這可讓相片大小最多可達648圖元乘648圖元。</span><span class="sxs-lookup"><span data-stu-id="57dff-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="57dff-106">此外, Exchange Server 可以根據需要自動調整這些相片的大小, 以供不同的產品使用。</span><span class="sxs-lookup"><span data-stu-id="57dff-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="57dff-107">通常這表示三種不同的相片大小與解析度:</span><span class="sxs-lookup"><span data-stu-id="57dff-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="57dff-108">64圖元乘64圖元, 此為 Active Directory thumbnailPhoto 屬性所使用的大小。</span><span class="sxs-lookup"><span data-stu-id="57dff-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="57dff-109">如果您將相片上傳到 Exchange Server, Exchange 會自動建立64圖元 (由該相片的64圖元版本), 並更新使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="57dff-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="57dff-110">但請注意, 反之不是這樣: 如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性, 就不會自動更新使用者的 Exchange 信箱中的相片。</span><span class="sxs-lookup"><span data-stu-id="57dff-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="57dff-111">96圖元乘96圖元, 用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、商務用 Skype Web App 及商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="57dff-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="57dff-112">在商務用 Skype 和商務用 Skype Web App 商務用 skype Web App 中使用的648圖元乘648圖元。</span><span class="sxs-lookup"><span data-stu-id="57dff-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="57dff-113">如果您有這些資源, 建議您上傳 648 x 648 相片;可提供任何 Office 2013 應用程式中的最大解析度和最佳圖片品質。</span><span class="sxs-lookup"><span data-stu-id="57dff-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="57dff-114">每個大小為 648 x 648 且深度為24位的 JPEG 相片, 都會產生大約 240 kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="57dff-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="57dff-115">這表示每4個使用者相片都需要大約 1 mb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="57dff-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="57dff-116">使用 Exchange Web 服務存取的高解析度相片, 可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。</span><span class="sxs-lookup"><span data-stu-id="57dff-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="57dff-117">不過, 管理員可以使用 Exchange 管理命令介面和一系列類似下列的 Windows PowerShell 命令來更新任何使用者的相片:</span><span class="sxs-lookup"><span data-stu-id="57dff-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="57dff-118">前面範例中的第一個命令會使用`Get-Content` Cmdlet 來讀取檔案 C:\Photos\Kenmyer.jpg 的內容, 並將該資料儲存在名為 $photo 的變數中。</span><span class="sxs-lookup"><span data-stu-id="57dff-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="57dff-119">在第二個命令中, 會`Set-UserPhoto`使用 Exchange Cmdlet 來上傳相片, 並將該相片附加到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="57dff-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57dff-120">在這個範例中, Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="57dff-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="57dff-121">您也可以使用其他識別碼 (例如使用者的 SMTP 位址或其使用者主要名稱) 來參考使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="57dff-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="57dff-122">[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)如需詳細資訊, 請參閱 UserPhoto Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="57dff-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="57dff-123">上傳相片並不相當於將該相片指派給 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="57dff-123">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="57dff-124">相反地, 上傳相片只會產生該相片的預覽, 以顯示在 Outlook Web App 的 [選項] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="57dff-124">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="57dff-125">若要將該相片實際指派給使用者帳戶, 使用者必須在 [選項] 頁面上按一下 [**儲存**], 否則系統管理員必須執行範例中的第三個命令。</span><span class="sxs-lookup"><span data-stu-id="57dff-125">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="57dff-126">第三個命令使用 Save 參數, 將相片指派給 Ken Myer 的使用者帳戶:</span><span class="sxs-lookup"><span data-stu-id="57dff-126">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="57dff-127">若要確認已將新相片指派給使用者帳戶, Ken Myer 可以登入商務用 Skype, 選取 [**選項**], 然後選取 [**我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="57dff-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="57dff-128">新上傳的相片應該顯示為 Ken 個人相片。</span><span class="sxs-lookup"><span data-stu-id="57dff-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="57dff-129">或者, 管理員可以啟動 Internet Explorer 並流覽至如下所示的 URL, 以驗證任何使用者的相片:</span><span class="sxs-lookup"><span data-stu-id="57dff-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="57dff-130">如果系統管理員可以使用 Internet Explorer 來查看相片, 但是使用者無法在商務用 Skype 中查看他或她的相片, 可能是 Exchange Web 服務或 Exchange 自動探索服務的連線問題。</span><span class="sxs-lookup"><span data-stu-id="57dff-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="57dff-131">請注意, 在商務用 Skype 中, 您也不需要進行額外的設定, 就能使用這張相片。</span><span class="sxs-lookup"><span data-stu-id="57dff-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="57dff-132">相反地, 相片會在上傳後立即可用, 且已執行`Set-UserPhoto` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57dff-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
