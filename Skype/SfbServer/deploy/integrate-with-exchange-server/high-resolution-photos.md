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
ms.openlocfilehash: 1ca9c0077969cab22b8ebfa073d3d0585108503b
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464652"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>在商務用 Skype Server 中設定高解析度相片的使用方式
 
**摘要:** 在 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 中設定高解析度相片的使用。
  
在商務用 Skype Server 相片中, 您可以儲存在使用者的 Exchange Server 2016 或 Exchange Server 2013 信箱中, 這可讓相片大小最多可達648圖元乘648圖元。 此外, Exchange Server 可以根據需要自動調整這些相片的大小, 以供不同的產品使用。 通常這表示三種不同的相片大小與解析度:
  
- 64圖元乘64圖元, 此為 Active Directory thumbnailPhoto 屬性所使用的大小。 如果您將相片上傳到 Exchange Server, Exchange 會自動建立64圖元 (由該相片的64圖元版本), 並更新使用者的 thumbnailPhoto 屬性。 但請注意, 反之不是這樣: 如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性, 就不會自動更新使用者的 Exchange 信箱中的相片。
    
- 96圖元乘96圖元, 用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、商務用 Skype Web App 及商務用 Skype。
    
- 在商務用 Skype 和商務用 Skype Web App 商務用 skype Web App 中使用的648圖元乘648圖元。
    
> [!NOTE]
> 如果您有這些資源, 建議您上傳 648 x 648 相片;可提供任何 Office 2013 應用程式中的最大解析度和最佳圖片品質。 每個大小為 648 x 648 且深度為24位的 JPEG 相片, 都會產生大約 240 kb 的檔案大小。 這表示每4個使用者相片都需要大約 1 mb 的磁碟空間。 
  
使用 Exchange Web 服務存取的高解析度相片, 可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。 不過, 管理員可以使用 Exchange 管理命令介面和一系列類似下列的 Windows PowerShell 命令來更新任何使用者的相片:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

前面範例中的第一個命令會使用`Get-Content` Cmdlet 來讀取檔案 C:\Photos\Kenmyer.jpg 的內容, 並將該資料儲存在名為 $photo 的變數中。 在第二個命令中, 會`Set-UserPhoto`使用 Exchange Cmdlet 來上傳相片, 並將該相片附加到 Ken Myer 的使用者帳戶。
  
> [!NOTE]
> 在這個範例中, Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。 您也可以使用其他識別碼 (例如使用者的 SMTP 位址或其使用者主要名稱) 來參考使用者帳戶。 [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)如需詳細資訊, 請參閱 UserPhoto Cmdlet 的相關檔。
  
上傳相片並不相當於將該相片指派給 Ken Myer 的使用者帳戶。 相反地, 上傳相片只會產生該相片的預覽, 以顯示在 Outlook Web App 的 [選項] 頁面上。 若要將該相片實際指派給使用者帳戶, 使用者必須在 [選項] 頁面上按一下 [**儲存**], 否則系統管理員必須執行範例中的第三個命令。 第三個命令使用 Save 參數, 將相片指派給 Ken Myer 的使用者帳戶:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

若要確認已將新相片指派給使用者帳戶, Ken Myer 可以登入商務用 Skype, 選取 [**選項**], 然後選取 [**我的圖片**]。 新上傳的相片應該顯示為 Ken 個人相片。 或者, 管理員可以啟動 Internet Explorer 並流覽至如下所示的 URL, 以驗證任何使用者的相片:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

如果系統管理員可以使用 Internet Explorer 來查看相片, 但是使用者無法在商務用 Skype 中查看他或她的相片, 可能是 Exchange Web 服務或 Exchange 自動探索服務的連線問題。
  
請注意, 在商務用 Skype 中, 您也不需要進行額外的設定, 就能使用這張相片。 相反地, 相片會在上傳後立即可用, 且已執行`Set-UserPhoto` Cmdlet。
