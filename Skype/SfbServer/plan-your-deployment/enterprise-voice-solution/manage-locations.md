---
title: 在商務用 Skype Server 中管理 SIP 主幹服務提供者的位置
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 若要使用 SIP 主幹提供者規劃 E9-1-1 部署的位置資訊資料庫或類似外部資料庫，請在商務用 Skype Server 企業語音中作出必要的決策。
ms.openlocfilehash: 0c9adec0a213cfc726464285e93af14905b8dd49
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398727"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 SIP 主幹服務提供者的位置

若要使用 SIP 主幹提供者規劃 E9-1-1 部署的位置資訊資料庫或類似外部資料庫，請在商務用 Skype Server 企業語音中作出必要的決策。

若要設定商務用 Skype Server 自動在網路中尋找用戶端，您必須使用網路線路圖填入位置資訊服務資料庫，併發布位置，或連結至已經包含正確對應的外部資料庫。 在此程式中，您必須使用 E9-1-1 服務提供者驗證位置的市政位址。 如需詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) 。

您可以使用 ERL) （包含市政位址及大樓內的特定位址） (的 [緊急回應] 位置，填入位置資訊服務資料庫。 位置資訊服務 **位置** 欄位是大樓內的特定位置，其最大長度為20個字元 (包含空格) 。 在此有限長度內，嘗試包含下列專案：

- 易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。 此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。 避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。

- 可協助使用者輕鬆查看其商務用 Skype 用戶端是否已挑選正確位置的位置識別碼。 商務用 Skype 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。 最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 \<street number> " ) 。 沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。

- 如果該位置是由無線存取點所決定，您可以新增 **[near]** (例如，「接近第一層1234」 ) 。

> [!NOTE]
> 新增至中央位置資料庫的位置直到使用商務用 Skype Server 管理命令介面命令加以發佈，而且會複製到集區的本機存放區，才可供用戶端使用。 如需詳細資訊，請參閱部署檔中 [的發佈位置資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) 。

下列各節討論在填充及維護位置資料庫時，需要考慮的考慮事項。

## <a name="populating-the-location-database"></a>填充位置資料庫

下列問題可協助您決定如何填入位置資料庫。

 **您將使用哪個程式填入位置資料庫？**

資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？ 是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？

 **您是否有已包含位置對應的協力廠商資料庫？**

使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。 這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。 這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址給商務用 Skype 用戶端。 然後，使用者可以選擇最適合的位置。

若要與位置資訊服務整合，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。 如需詳細資訊，請參閱  [[E911WS]： E911 支援通訊協定規格的 Web 服務]](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)。 如需部署次要位置資訊服務的詳細資訊，請參閱部署檔[中的商務用 Skype Server 設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。

如需有關填充位置資料庫的詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) 。

## <a name="maintaining-the-location-database"></a>維護位置資料庫

填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。 下列問題可協助您決定如何維護位置資料庫。

 **您將如何更新位置資料庫？**

有幾個案例需要更新位置資料庫，包括新增 Wap、office recabling (產生不同的切換指派) 及子網擴充。 您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？

 **您是否會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠及切換識別碼對應？**

如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。 如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。