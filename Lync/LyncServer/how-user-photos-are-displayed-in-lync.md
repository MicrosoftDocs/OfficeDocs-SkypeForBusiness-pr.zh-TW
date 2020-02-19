---
title: 在 Lync 使用者相片的顯示方式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097262cc3a4ba4b56cd023bc5174d881426deff2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>在 Lync 使用者相片的顯示方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-25_

**摘要：** 在 Lync 用戶端顯示的使用者相片可以使用，例如何時在會議或 IM 交談中的 Lync 功能而有所不同。

Lync 2010 推出的功能包括與您要顯示給其他 Lync 使用者的 Lync 設定檔相片。 您也可以選擇要在 Lync 用戶端中顯示為連絡人的相片。 Lync 2013 中支援的高解析度相片的使用者。 本主題說明如何取得 Lync 用戶端，並會顯示使用者相片，儲存影像、 每個影像來源，限制及如何將使用者相片使用不同的 Lync 服務。

<div>

## <a name="planning-considerations"></a>規劃考量

若要實作使用者相片支援規劃時，您應該考慮下列。

  - 高畫質使用者相片支援需要使用者的信箱會位於 Exchange 2013 和 Lync 使用者帳戶是 Lync 2013 集區中。

  - 使用 Lync Server 2013 和 Exchange 2013 環境中僅支援高畫質使用者相片。

  - 使用信箱位於 Exchange 2010 上的使用者將會一律用於從 AD DS 的**thumbnailPhoto**屬性做為來源其使用者相片。

  - 使用者相片儲存為從 AD DS 的**thumbnailPhoto**屬性不會顯示外部 / 同盟連絡人。

  - 如果使用者連絡人相片儲存在 AD DS 中，所使用之影像檔案是限制為 96 × 96 像素為單位並不超過 100 KB 的檔案大小。

  - Lync Server 與 Exchange 伺服器之間的連線會遺失，如果從 AD DS 的使用者的低解析度**thumbnailPhoto**就會顯示，並為內部使用者。

  - 當前發言者沒有啟用的影片時，高解析度的使用者相片會顯示 Lync 2013 會議中。 此外，將滑鼠移 over 縮圖相片藝廊中會顯示高解析度相片。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 中的使用者相片

在 Lync 2010 用戶端上，您可以選擇從兩個選項來顯示您的設定檔，將相片**預設公司圖片**並**顯示從網址的圖片**。

<div>

## <a name="default-corporate-picture"></a>預設公司圖片

當您選擇 [**預設公司圖片**] 選項時，Lync 取得從 Active Directory 網域服務顯示為您的相片。 使用的影像是指在 Active Directory 網域服務中的**thumbnailPhoto**屬性的值的圖像。 這是 Exchange 所用來在 Outlook 中顯示圖像的同一個檔案。

使用影像從 Active Directory 網域服務的考量包括：

  - 支援最多 96 像素 x 96 像素為單位的尺寸大小的映像。 影像的檔案大小是限制為 100 KB。

  - 根據預設，使用者便能夠變更影像用於的**thumbnailPhoto**屬性，但是不會直接透過 Lync 用戶端。 您可以透過 Active Directory 網域服務來停用此設定。

  - 即使是同盟的連絡人，儲存在 Active Directory 網域服務中的影像不會顯示您組織外部的連絡人。

  - 在大型組織中，儲存及擷取大量使用者的影像可能會影響效能與 Active Directory 網域服務資料庫的大小。

  - 有限的影像大小與檔案大小代表的意義，可以使用僅限低解析度影像。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>使用者如何管理 Active Directory 網域服務中的其使用者相片

使用者無法變更其 Active Directory 網域服務的設定檔直接透過 Lync 2010 用戶端中使用的影像。 他們可以使用下列選項之一若要這麼做，如果有：

  - **SharePoint Server**   使用者可以上傳相片與 ' 「 我的網站 」 上 SharePoint 伺服器，並接著[設定設定檔同步處理 sharepoint](https://go.microsoft.com/fwlink/p/?linkid=507466)同步處理 Active Directory 網域服務中的**thumbnailPhoto**屬性的相片。

  - **可公開存取的 URL 上儲存的相片**   使用者可以設定指定的影像他們想要使用可公開存取 URL 其使用者相片。 影像必須是不需要密碼可公開存取。 儲存在指定的網址的影像會被轉接至其他使用者透過 [連絡人卡片] 類別中的目前狀態資訊。 當 Lync 用戶端需要顯示使用者相片時，它會從指定的網頁地址擷取映像。

  - **Windows powershell 的 Exchange 2010 cmdlet**   系統管理員可以管理的**thumbnailPhoto**屬性中的 Exchange 2010 管理命令介面中執行[Import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468)指令程式。 當影像匯入與 Exchange 2010 cmdlet 的檔案大小是限制為 10 KB。

  - **協力廠商工具**   使用者可以上傳僅限自己相片與**thumbnailPhoto**屬性。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>顯示來自網址的圖片

當您選擇 [**顯示來自網址的圖片**] 選項時，Lync 會取得圖像處輸入，並將其顯示為您的使用者相片 Lync 中的地址。

下面是使用影像網頁的地址的注意事項：

  - 檔案大小限制會取決於**MaxPhotoSizeKB**屬性在用戶端原則中，使用[New-csclientpolicy](https://go.microsoft.com/fwlink/p/?linkid=507463)指令程式來定義。 預設的大小限制為 30 KB。 最大值為 100 KB。 在此映像的解析度沒有限制，但如果您嘗試使用映像檔超過大小限制，它將不會下載到 Lync 用戶端。 您可以設定此值為 0，即可停用 Lync 中使用的所有使用者相片。

  - 外部同盟連絡人可以看到從網址的使用者相片。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>管理使用者的相片與用戶端原則指令程式

在 Lync Server 2010 中，用戶端原則設定來設定 CsClientPolicy 指令程式。 設定的原則設定會傳送至用戶端透過頻內佈建。 決定使用者相片體驗 CsClientPolicy cmdlet 的兩個參數，而**DisplayPhoto** **MaxPhotoSizeKB**。 **DisplayPhoto**和**MaxPhotoSizeKB**對應的頻內佈建參數是名為**PhotoUsage**。 **PhotoUsage**參數的值是透過**endpointConfiguration** **provisionGroup**的用戶端傳送。 如需詳細資訊，請參閱[概觀的用戶端原則和設定](https://go.microsoft.com/fwlink/?linkid=507470)。

**DisplayPhoto**參數值會決定使用者的相片影像的來源。 下列資料表中所含之支援的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 參數值</th>
<th>影像來源</th>
<th>Lync 2010 用戶端設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nophoto:</p></td>
<td><p>無</p></td>
<td><p><strong>不顯示我的圖片</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>預設公司圖片</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>網址</p></td>
<td><p><strong>顯示來自網址的圖片</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 用戶端如何取得相片

在 Lync 2010 中，使用者相片會在伺服器上管理通訊錄服務。 Lync 用戶端第一個查詢公開透過通訊群組清單擴充 web 服務的伺服器上的地址通訊錄 Web 查詢 (ABWQ) 服務來取得使用者相片。 用戶端接收的影像檔，並再將它複製到使用者的快取，以避免下載映像需要顯示每次。 從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務項目。 通訊錄服務會刪除所有快取的影像每隔 24 小時，這表示，可能需要 24 小時的時間進行更新的新使用者影像的伺服器上快取中。 您可以使用[Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet 強制執行更新快取。

包含在目前狀態的使用者相片也具有 Lync 用戶端用來判斷是否有可用的較新的圖像相關聯的雜湊值。 用戶端會自動收到的使用中的目前狀態的影像檔案的變更通知。

<div class=" ">


> [!NOTE]  
> 因為相片不會儲存在 GalContacts.db 資料庫中，下載使用者相片不是取決於用戶端原則 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-csclientpolicy</A>) 中 [ <STRONG>AddressBookAvailability</STRONG>設定。



</div>

ABWQ 服務查詢包含下列屬性：

  - **PhotoHash**   雜湊資料的值二進位相片，而且會用來判斷是否已變更目前的相片。

  - **PhotoRelPath**   影像檔案儲存在伺服器上的相對路徑。

  - **PhotoSize**   影像檔，以位元組為單位的大小。

  - **時間戳記**   的日期和時間的影像檔上次從伺服器下載並複製到用戶端快取。

接下來之後擷取映像檔，Lync 2010 用戶端比較，看看它們是否不同用戶端從頻內佈建接收到的屬性值對查詢所傳回的屬性值。 如果值不同，用戶端會擷取 HTTP GET 要求的登入使用者的圖像檔案。

此外，用戶端檢查與伺服器進行比較的值在用戶端上的伺服器上**PhotoHash**屬性的值建立影像檔案的快取的版本的速率時間從每隔 24 小時。 如果值不同，用戶端會知道已變更，圖像檔案。 若要取得更新的影像檔案，用戶端重新查詢 ABWQ 要更新的服務用戶端快取中的影像檔與影像檔案在伺服器上，這也會重設**的時間戳記**的用戶端快取中的檔案。

以下是將查詢傳送至 ABWQ 服務範例回應：
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

## <a name="user-photos-in-lync-2013"></a>Lync 2013 中的使用者相片

Lync 2013 引進了使用者相片高解析度影像的支援。 Lync 2013 還包含支援將使用者相片儲存在使用者的信箱在 Exchange 2013 中，會移除映像的解析度和 Lync 2010 中呈現的大小限制。 Lync 2013 中的使用者相片可以最多 648 像素 x 648 像素，最多 20 MB 的檔案大小。 在 Lync 2013 的高解析度相片必須位於 Exchange 2013 中，使用者的信箱，並只支援 Lync 2013 用戶端。 這與 Exchange 整合善用 Lync、 Exchange 和稱為 Oauth 的 SharePoint 2013 版本中包含的新授權架構。

如果 Exchange 2013 不適用於您的部署，支援的使用者相片與 Lync 2010 相同。 不過，若要選擇使用相片使用者選項各有不同 Lync 2013 用戶端中。 在 Lync 2013 用戶端，使用者可以選取 [**隱藏我的圖片**] 或 [**顯示我的圖片**。 **顯示網站中的圖片**] 選項不是依預設，可使用，但可以藉由將用戶端原則指派啟用。

<div>

## <a name="hide-my-picture"></a>隱藏我的圖片

使用者相片設定不在 Lync 2013 中的 [**選項**] 對話方塊。 當您選擇**隱藏我的圖片**時，沒有使用者相片會顯示為您在 Lync 用戶端，但在您的連絡人卡片上及 Lync 外，仍顯示相片。

</div>

<div>

## <a name="show-my-picture"></a>顯示我的圖片

當您選擇 [**顯示我的圖片**] 選項時，您的使用者相片會顯示在您的 Lync 用戶端，並將 Lync 交談中的其他使用者。 使用的影像是儲存在 AD DS。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>顯示網站中的圖片

**顯示從網站的圖片**] 選項可在 Lync 2013 後的用戶端原則設為啟用它。 用戶端版本必須比 15.0.4535.1002，則會以安裝更新[Lync 累計更新： 11 月 2013年](https://go.microsoft.com/fwlink/p/?linkid=509908)。 使用者可能需要登出，然後再重新中若要查看在用戶端的變更。

您可以設定用戶端原則，以便**顯示從網站的圖片**設定 Lync Server 管理命令介面中執行的[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則。 下列範例指令程式會示範如何部署中的所有使用者的全域設定的原則：

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


當影像上傳到使用者的信箱時，Exchange 會自動建立的影像，可以使用的低解析度版本用戶端應用程式中。 使用者相片也會更新 AD DS 中。

<div class=" ">


> [!NOTE]  
> 當影像檔案更新 AD DS 中時，48 x 48 像素影像建立，並使用 AD DS 中 thumbnailPhoto。 會取代任何現有的影像。 因此如果您已為 96 x 96 影像新增至 AD DS，它會覆寫新 48 x 48 圖像。 這是只有重要是您使用 Lync 2010 用戶端，您環境中有使用者，因為這些用戶端會從 AD DS 取得使用者相片。 您可以匯入來取代有 Lync 2010 用戶端在組織中建立的 AD DS 的那些 96 x 96 像素影像。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 中的使用者相片支援

在 Lync 2013 中，三個圖像解析度支援使用者相片，如下表所述。 使用影像取決於指派給 Lync 使用者的用戶端原則設定。 「 管理使用者的相片與用戶端原則指令程式搭配 「 在此主題以取得詳細資訊，請參閱。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>影像解析度 （像素為單位）</th>
<th>應用程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>如果已選取 [沒有高解析度影像</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Outlook Web App 和 Outlook 2013 中使用</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Lync 2013 桌面用戶端和 Lync 2013 Web 應用程式中使用</p></td>
</tr>
</tbody>
</table>


任何具有 Exchange 2013 中啟用信箱的使用者可以上傳不同的映像，包括高解析度相片，透過 Outlook Web Access 或 Lync 2013 用戶端選項。 所用的圖像的建議的設定包括：

  - **影像解析度**   648 由 648 像素為單位

  - **色彩深度**   24 位元

  - **影像檔案大小**   設為 20 MB

  - **檔案格式**   JPEG

為 648 像素 x 648 像素為單位的一般 24 位元 JPEG 圖像有檔案大小約為 240 kb，所以 1 MB 的儲存空間所需的每個 4 使用者相片。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

