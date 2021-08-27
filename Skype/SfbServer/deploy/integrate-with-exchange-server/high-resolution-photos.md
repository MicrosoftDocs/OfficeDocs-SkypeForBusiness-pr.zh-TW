---
title: 在商務用 Skype Server 中設定高解析度相片的使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要：設定高解析度相片的使用 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013，或是 Exchange Online 及商務用 Skype Server。
ms.openlocfilehash: d82a8aa665a699e7589a3a477023be55ea0407ea
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621795"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>在商務用 Skype Server 中設定高解析度相片的使用
 
**摘要：** 設定 Exchange Server 2019 的高解析度相片，Exchange Server 2016，Exchange Server 2013，或 Exchange Online 及商務用 Skype Server。
  
在商務用 Skype Server 中，相片可以儲存在使用者的 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 信箱中，這可讓相片大小高達648圖元的648圖元。 此外，Exchange Server 可以視需要自動調整這些照片的大小，以供不同的產品使用。 通常是指三種不同的相片大小和解析度：
  
- 64圖元 x 64 圖元，使用 Active Directory thumbnailPhoto 屬性的大小。 若要將相片上傳至 Exchange Server，Exchange 會自動建立64圖元乘以該相片的64圖元版本，並更新使用者的 thumbnailPhoto 屬性。 不過，請注意，reverse 相反：如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性，將不會自動更新使用者 Exchange 信箱中的相片。
    
- 96圖元 x 96 圖元，以用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、商務用 Skype Web 應用程式及商務用 Skype。
    
- 648圖元 x 648 圖元，供商務用 Skype 和商務用 Skype Web 應用程式商務用 Skype Web 應用程式使用。
    
> [!NOTE]
> 如果您有資源，建議您上傳 648 x 648 相片;，可提供任何 Office 2013 應用程式的最大解析度及最佳圖片品質。 每個大小為 648 x 648 且深度為24位的 JPEG 相片會產生大約 240 kb 的檔案大小。 這表示每4個使用者相片需要大約 1 mb 的磁碟空間。 
  
使用 Exchange web 服務來存取的高解析度相片，可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。 不過，系統管理員可以使用 Exchange 管理命令介面和如下一系列的 Windows PowerShell 命令，更新任何使用者的相片：
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

上一個範例中的第一個命令會使用 `Get-Content` Cmdlet 讀取檔案 C:\Photos\Kenmyer.jpg 的內容，並將該資料儲存在名為 $photo 的變數中。 在第二個命令中，Exchange Cmdlet `Set-UserPhoto` 是用於上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。
  
> [!NOTE]
> 在此範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。 您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。 如需詳細資訊，請參閱 Set-UserPhoto Cmdlet 的檔 [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) 。
  
上傳相片不會像指派該相片到 Ken Myer 的使用者帳戶。 相反地，上載照片只會導致預覽該相片顯示在 [Outlook Web App 選項] 頁面上。 若要將該相片實際指派給使用者帳戶，使用者必須按一下 [選項] 頁面上的 [ **儲存** ]，否則系統管理員必須執行範例中的第三個命令。 第三個命令使用 Save 參數將相片指派給 Ken Myer 的使用者帳戶：
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

若要確認是否已將新的相片指派給使用者帳戶，Ken Myer 可以登入商務用 Skype，選取 [**選項**]，然後選取 [**我的圖片**]。 新上傳的相片應顯示為 Ken 的個人照片。 或者，系統管理員可以啟動 Internet Explorer，並流覽至類似下列的 URL，以確認任何使用者的相片。
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

如果系統管理員可以使用 Internet Explorer 來查看照片，但是使用者無法在商務用 Skype 中查看其照片，可能是 Exchange Web 服務或 Exchange 自動探索服務的連線問題。
  
請注意，您也不需要進行其他設定，即可在商務用 Skype 中使用此相片。 相反地，照片會在上傳後立即可用，而且已 `Set-UserPhoto` 執行 Cmdlet。