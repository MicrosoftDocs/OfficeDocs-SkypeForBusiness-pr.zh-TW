---
title: Lync Server 2013： 管理 ELIN 閘道位置
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
ms.openlocfilehash: 17fa27b82260a05ded5ca025d56005c864247844
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>管理 ELIN 閘道 Lync Server 2013 中的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

若要讓 Lync Server 自動提供網路內的用戶端的位置，您需要執行下列工作：

  - 填入網路接線圖，位置資訊服務資料庫，並在 CompanyName 欄位中包含緊急事故位置識別碼 (Elin)。

  - 發佈位置，使其可供您網路中的用戶端。

  - 將 Elin 上傳至您的公用交換的電話網路 (PSTN) 電信業者的自動位置識別 (ALI) 資料庫。

如需如何執行這些工作的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。

<div>


> [!NOTE]  
> 除非他們已發佈使用 Lync Server 管理命令介面命令，並且會複寫到集區的本機存放區，並不適用於用戶端新增至中央位置資料庫的位置。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publish-the-location-database.md">發佈位置資料庫從 Lync Server 2013</A> 。



</div>

本節說明當您規劃更新和維護位置資料庫的考量事項。

<div>

## <a name="planning-emergency-locations"></a>規劃緊急事故處理位置

當您使用 ELIN 閘道時，您會填入市街地址、 建置內的特定位置與至少一個 ELIN 為每個位置的位置資訊服務資料庫。 計劃階段中，它是不錯的選項，以決定要如何命名位置，以及您想要指派 Elin 的方式。

<div>

## <a name="planning-location-names"></a>規劃位置名稱

[位置資訊服務**位置**] 欄位中含有建置內的特定位置，具有長度上限為 20 個字元 （包括空格）。 在該限制的長度，嘗試包括下列各項：

  - 容易理解名稱，可識別 911 來電者可協助您確保的緊急回應者的特定位置迅速時找到它們都會送達市街地址的位置。 此位置名稱可能包含建築物編號、 底板數字、 蝶形指示項，會議室號碼等等。 避免只已知可能會導致移至錯誤的位置的緊急回應者的員工的暱稱。

  - 協助使用者輕鬆地查看，挑選的正確位置其 Lync 用戶端位置識別碼。 Lync 用戶端會自動將串連，並顯示探索到的**位置**] 和 [**縣/市**欄位標頭中。 很好的作法是將建置的街道地址新增至每個位置識別碼 (例如，"1st Floor\<街道號碼\>」)。 街道地址，而 「 1st 樓 」 等的一般位置識別碼無法套用至任何建置在 [縣/市。

  - 如果因為它由無線存取點決定的概略位置，您可能想要加入 near 的字詞 （例如 「 靠近 1st 樓 1234年）。

</div>

<div>

## <a name="planning-elins"></a>規劃 Elin

決定您要建置空間分成數個位置的方式之後，您需要決定多少 Elin 指派給每個位置。 例如，multifloor 或在多租用戶的建置、 中建置不同的區域可以指派不同的緊急區域。 一般而言，每個樓層建置已指定位置。 每個位置就被指派一或多個 Elin 時，緊急通話當成通話轉接。 您可以使用 Elin 的電話號碼，請連絡您 PSTN 電信業者。 下表提供特定的街道地址的位置的範例。

### <a name="sample-location-and-elin-assignments"></a>範例位置和 ELIN 指派作業

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
<td><p>一樓</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>二樓</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>三樓</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


您定義的位置應符合下列需求：

  - 遵守本機和國家/區域法令每個位置及每個街道地址的位置數目的最大區域。

  - 特有足以讓您輕鬆找到緊急來電者。

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>填入位置資料庫

下列問題可協助您決定如何填入位置資料庫。

  - **您將使用何種程序填入位置資料庫？**  
    其中是否存在的資料，以及您需要將資料轉換成位置資料庫所需的格式採取哪些步驟？ 將您新增位置會個別或大量使用 CSV 檔案？

<!-- end list -->

  - **您必須已經包含位置對應的協力廠商資料庫？**  
    使用 Lync Server 的次要位置資訊服務] 選項，以連線至協力廠商資料庫，您可以群組，並使用離線平台管理位置。 這種方法的好處是，除了建立關聯至網路識別碼的位置，您可以建立關聯的使用者的位置。 這表示位置資訊服務可以傳回多個地址，源自次要位置資訊服務，Lync Server 用戶端。 然後，使用者可以選擇最適合的位置。
    
    若要整合與位置資訊服務，協力廠商資料庫必須遵循 Lync 伺服器位置要求讀回應結構描述。 如需詳細資訊，請參閱<https://go.microsoft.com/fwlink/p/?linkid=213819>。 如需部署次要位置資訊服務的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。

如需填入位置資料庫的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>維護位置資料庫

填入位置資料庫之後，您需要開發更新資料庫作為網路組態變更的策略。 下列問題可協助您決定如何維護位置資料庫。

  - **您要如何更新位置資料庫？**  
    有幾種情況，需要更新至位置資料庫，包括新增無線存取點 (Wap)、 office recabling （產生不同的參數指派），和子網路擴充。 將您直接更新每個個別的位置，或將使用 CSV 檔案來執行的所有位置大量更新？

<!-- end list -->

  - **您將使用 SNMP 應用程式符合 Lync 用戶端 MAC 位址來連接埠和交換器識別碼？**  
    如果您使用 SNMP 應用程式，您需要開發將交換器底座和連接埠資訊保持一致 SNMP 應用程式和資料庫位置之間的手動程序。 如果 SNMP 應用程式傳回底座 IP 位址或連接埠編號不包含在資料庫中，將位置資訊服務將無法傳回給用戶端的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

