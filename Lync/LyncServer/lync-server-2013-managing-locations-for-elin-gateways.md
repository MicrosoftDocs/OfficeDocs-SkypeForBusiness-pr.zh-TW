---
title: Lync Server 2013：管理 ELIN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>在 Lync Server 2013 中管理 ELIN 閘道的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

若要讓 Lync Server 在網路中自動提供用戶端位置，您必須執行下列工作：

  - 使用網路 wiremap 填入位置資訊服務資料庫，並在 [公司名稱] 欄位中包含緊急位置識別號碼（ELINs）。

  - 發佈位置，讓您的網路上的客戶可以使用它們。

  - 將 ELINs 上傳到您的公用交換電話網絡（PSTN）電信公司的自動位置識別（阿裡）資料庫。

如需如何執行這些工作的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)。

<div>


> [!NOTE]  
> 您必須先使用 Lync Server 管理命令介面命令發佈的位置，並複製到該池的本機存儲區，才能讓該用戶端無法使用新增到中央位置資料庫的位置。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-publish-the-location-database.md">從 Lync Server 2013 發佈位置資料庫</A>。



</div>

本節說明您規劃更新及維護位置資料庫時應考慮的事項。

<div>

## <a name="planning-emergency-locations"></a>規劃緊急位置

當您使用 ELIN 閘道時，您會使用市政位址、組建中的特定位置，以及為每個位置至少一個 ELIN 來填入位置資訊服務資料庫。 在規劃階段，最好決定您要如何命名位置，以及您想要如何指派 ELINs。

<div>

## <a name="planning-location-names"></a>規劃位置名稱

[位置資訊服務**位置**] 欄位會存放建築物內的特定位置，最大長度為20個字元（包括空格）。 在該長度有限的範圍內，嘗試包含下列專案：

  - 識別911呼叫者位置的易於理解的名稱，可協助確保緊急回應程式在到達市政位址時能快速找到特定位置。 這個位置名稱可以包含建築物編號、樓層編號、翼標示符、房間號碼等。 避免只提供給員工的昵稱，這可能會導致緊急回應程式移至錯誤的位置。

  - 可協助使用者輕鬆查看其 Lync 用戶端是否已挑選正確位置的位置識別碼。 Lync 用戶端會自動連接，並在其頁首中顯示 [已探索的**位置**] 和 [**城市**] 欄位。 最好的做法是將建築物的街道位址新增至每個位置識別碼（例如，「第一層\<街道編號\>」）。 如果沒有街道位址，一般位置識別碼（例如「第一層」）會套用至城市中的任何建築物。

  - 如果該位置是由無線存取點所決定，您可能會想要在附近新增一個字（例如，「接近第一層1234」）。

</div>

<div>

## <a name="planning-elins"></a>規劃 ELINs

在您決定要如何將建築物空間劃分至多個位置之後，您必須決定要將多少 ELINs 指派給每個位置。 例如，在 multifloor 或多租戶組建中，組建中的不同區域可以指定不同的緊急區域。 一般來說，建築物中的每個樓層都指定為一個位置。 接著，系統會為每個位置指派一個或多個 ELINs，在緊急通話期間，就會用來做為電話號碼。 請與您的 PSTN 運營商聯繫，以取得您可以用來 ELINs 的電話號碼。 下表提供特定街道位址的位置範例。

### <a name="sample-location-and-elin-assignments"></a>範例位置與 ELIN 作業

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>建築物區域</th>
<th>位置</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>第一層</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>第二層</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>第三層</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


您定義的位置應該符合下列需求：

  - 在每個位置的最大區域及每個街道位址的位置數方面，遵守當地和國家/地區管理法規。

  - 都有足夠的針對性，便於您找到緊急來電者。

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>填充位置資料庫

下列問題將協助您決定將如何填入位置資料庫。

  - **您將使用哪個程式來填入位置資料庫？**  
    資料在哪裡存在，您需要採取哪些步驟才能將資料轉換成位置資料庫所需的格式？ 您會使用 CSV 檔案個別地新增位置，還是大量新增位置？

<!-- end list -->

  - **您是否有已包含位置對應的協力廠商資料庫？**  
    透過使用 Lync Server 的 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組及管理位置。 這種方法的優點是，除了將位置與網路識別碼相關聯之外，您還可以將位置與使用者建立關聯。 這表示位置資訊服務可以傳回多個位址（源自次要位置資訊服務）至 Lync Server 用戶端。 然後，使用者可以選擇最適合的位置。
    
    若要整合位置資訊服務，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。 如需詳細資訊<http://go.microsoft.com/fwlink/p/?linkid=213819>，請參閱。 如需有關部署次要位置資訊服務的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。

如需有關填充位置資料庫的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>維護位置資料庫

在您填入 location 資料庫之後，您需要開發一個策略，在網路設定變更時更新資料庫。 下列問題將協助您決定如何維護位置資料庫。

  - **如何更新位置資料庫？**  
    有幾種情況需要更新位置資料庫，包括新增無線存取點（WAPs）、office recabling （產生不同的切換作業），以及子網延伸。 您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？

<!-- end list -->

  - **您會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠和交換器識別碼搭配使用嗎？**  
    如果您使用的是 SNMP 應用程式，您必須開發手動程式，以保持 SNMP 應用程式和位置資料庫之間的切換底盤和埠資訊一致。 如果 SNMP 應用程式傳回的是不包含在資料庫中的主機殼 IP 位址或埠 ID，位置資訊服務將無法傳回用戶端的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

