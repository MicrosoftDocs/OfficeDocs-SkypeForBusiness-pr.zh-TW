---
title: Lync Server 2013： 管理 SIP 主幹服務提供者的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8be19c6ca5aad78bc82487d8208fb163f62fbcb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>管理 Lync Server 2013 中的 SIP 主幹服務提供者的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

若要設定自動尋找網路內的用戶端的 Lync Server，您需要填入網路接線圖位置資訊服務資料庫及發佈的位置，或連結至已經包含正確的外部資料庫對應。 此程序的一部分，您需要驗證 E9-1-1 服務提供者那邊位置的市街地址。 如需詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。

您填入位置資訊服務資料庫與緊急回應位置 (ERL)，其中包括市街地址和建置內的特定地址。 位置資訊服務**位置**] 欄位中，也就是建置內的特定位置，具有長度上限為 20 個字元 （包括空格）。 在該限制的長度，嘗試包括下列各項：

  - 容易理解名稱，可識別 911 來電者可協助您確保的緊急回應者的特定位置迅速時找到它們都會送達市街地址的位置。 此位置名稱可能包含建築物編號、 底板數字、 蝶形指示項，會議室號碼等等。 避免只有知道可能會導致移至錯誤的位置的緊急回應者的員工的暱稱。

  - 協助使用者輕鬆地查看，挑選的正確位置其 Lync 用戶端位置識別碼。 Lync 用戶端會自動將串連，並顯示探索到的**位置**] 和 [**縣/市**欄位標頭中。 很好的作法是將建置的街道地址新增至每個位置識別碼 (例如，"1st Floor\<街道號碼\>」)。 街道地址，而 「 1st 樓 」 等的一般位置識別碼無法套用至任何建置在 [縣/市。

  - 如果因為它由無線存取點決定的概略位置，您可以加入 near 的字詞 （例如 「 靠近 1st 樓 1234年）。

<div>


> [!NOTE]  
> 除非他們發佈使用 Lync Server 管理命令介面命令，並且會複寫到集區的本機存放區，並不適用於用戶端新增至中央位置資料庫的位置。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publish-the-location-database.md">發佈位置資料庫從 Lync Server 2013</A> 。



</div>

下列各節將討論您需要考慮當填入和維護位置資料庫時的考量。

<div>

## <a name="populating-the-location-database"></a>填入位置資料庫

下列問題可協助您決定如何填入位置資料庫。

  - **您將使用何種程序填入位置資料庫？**  
    其中是否存在的資料，以及您需要將資料轉換成位置資料庫所需的格式採取哪些步驟？ 將您新增位置會個別或大量使用 CSV 檔案？

<!-- end list -->

  - **您必須已經包含位置對應的協力廠商資料庫？**  
    使用 Lync Server 的次要位置資訊服務] 選項，以連線至協力廠商資料庫，您可以群組，並使用離線平台管理位置。 這種方法的好處是，除了建立關聯至網路識別碼的位置，您可以建立關聯的使用者的位置。 這表示位置資訊服務可以傳回多個地址，源自次要位置資訊服務，Lync Server 用戶端。 然後，使用者可以選擇最適合的位置。
    
    若要整合與位置資訊服務，協力廠商資料庫必須遵循 Lync 伺服器位置要求讀回應結構描述。 如需詳細資訊，請參閱 「\[MS E911WS\]: E911 支援通訊協定規格的 Web 服務 」 在<https://go.microsoft.com/fwlink/p/?linkid=213819>。 如需部署次要位置資訊服務的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。

如需填入位置資料庫的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>維護位置資料庫

填入位置資料庫之後，您需要開發更新資料庫作為網路組態變更的策略。 下列問題可協助您決定如何維護位置資料庫。

  - **您要如何更新位置資料庫？**  
    有幾種情況，需要更新至位置資料庫，包括新增 Wap、 office recabling （產生不同的參數指派），和子網路擴充。 將您直接更新每個個別的位置，或將使用 CSV 檔案來執行的所有位置大量更新？

<!-- end list -->

  - **您將使用 SNMP 應用程式符合 Lync 用戶端 MAC 位址來連接埠和交換器識別碼？**  
    如果您使用 SNMP 應用程式，您需要開發將交換器底座和連接埠資訊保持一致 SNMP 應用程式和資料庫位置之間的手動程序。 如果 SNMP 應用程式傳回底座 IP 位址或連接埠編號不包含在資料庫中，將位置資訊服務將無法傳回給用戶端的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

