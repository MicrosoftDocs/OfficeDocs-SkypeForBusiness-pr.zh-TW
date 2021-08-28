---
title: 在商務用 Skype Server 中管理 ELIN 閘道的位置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 使用 ELIN 閘道為 E9-1-1 的部署規劃位置資訊資料庫或類似的外部資料庫，在商務用 Skype Server 企業語音中所需的決策。
ms.openlocfilehash: bb0656909866a793bc8d64635b17785020dd646d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596503"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 ELIN 閘道的位置

使用 ELIN 閘道為 E9-1-1 的部署規劃位置資訊資料庫或類似的外部資料庫，在商務用 Skype Server 企業語音中所需的決策。

若要讓商務用 Skype Server 自動為網路中的用戶端提供位置，您必須執行下列工作：

- 以網路線路圖填入 Location 資訊服務資料庫，並在 [CompanyName] 欄位中包含緊急位置標識號 (Elin) 。

- 發佈位置，以供網路中的用戶端使用。

- Upload 您公用交換電話網路 (PSTN) 電信公司的自動位置識別， (阿裡) 資料庫中的 elin。

如需如何執行這些工作的詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) 。

> [!NOTE]
> 新增至中央位置資料庫的位置直到使用商務用 Skype Server 管理命令介面命令加以發佈，而且會複製到集區的本機存放區，才可供用戶端使用。 如需詳細資訊，請參閱部署檔中 [的發佈位置資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) 。

本節說明當您計畫更新及維護位置資料庫時，應考慮的事項。

## <a name="planning-emergency-locations"></a>規劃緊急位置

當您使用 ELIN 閘道時，會使用市政位址、大樓內的特定位置，以及每個位置至少一個 ELIN 來填入位置資訊服務資料庫。 在規劃階段期間，最好決定要如何命名位置，以及您要如何指派 Elin。

### <a name="planning-location-names"></a>規劃位置名稱

位置資訊服務 **位置** 欄位（容納大樓內的特定位置）的長度上限為20個字元 (包含空格) 。 在此有限長度內，嘗試包含下列專案：

- 易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。 此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。 避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。

- 一個位置識別碼，可協助使用者輕鬆地看到用戶端挑選的是正確的位置。 商務用 Skype 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。 最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 <street number> " ) 。 沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。

- 如果位置是由無線存取點所決定，您可能想要新增 **[near]** (例如，「接近第一層1234」 ) 。

### <a name="planning-elins"></a>規劃 Elin

決定如何將大樓空間分割成多個位置之後，您必須決定要將多少 Elin 指派給每個位置。 例如，在 multifloor 或多租戶組建中，可以將組建中的不同區域指派給不同的急診區域。 一般來說，大樓中的每一層都指定為位置。 然後將每個地點指派一或多個 Elin，在緊急通話期間會將其當作通話號碼 (s) 使用。 請與您的 PSTN 電信公司聯繫，以取得可用於 Elin 的電話號碼。 下表提供特定街道位址的位置範例。

**範例位置和 ELIN 指派**

|**組建區域**|**Location**|**愛琳**|
|:-----|:-----|:-----|
|第一層  <br/> |1   <br/> |425-555-0100  <br/> |
|第二個基底  <br/> |2   <br/> |425-555-0111  <br/> |
|第三個地板  <br/> |3   <br/> |425-555-0123  <br/> |

您定義的位置應符合下列需求：

- 在 [每個位置的最大區域] 和 [每個街道的位置數目] 等方面，遵循本機和國家/地區規定。

- 都有足夠的針對性，可讓您輕鬆找到緊急來電者。

## <a name="populating-the-location-database"></a>填充位置資料庫

下列問題可協助您決定如何填入位置資料庫。

 **您將使用哪個程式填入位置資料庫？**

資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？ 是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？

 **您是否有已包含位置對應的協力廠商資料庫？**

使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。 這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。 這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址給商務用 Skype 用戶端。 然後，使用者可以選擇最適合的位置。

若要與位置資訊服務整合，協力廠商資料庫必須遵循商務用 Skype Server 位置要求/回應架構。 如需詳細資訊，請參閱 [Web Service For E911 Support Protocol](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)。 如需部署次要位置資訊服務的詳細資訊，請參閱部署檔[中的商務用 Skype Server 設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。

如需有關填充位置資料庫的詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) 。

## <a name="maintaining-the-location-database"></a>維護位置資料庫

填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。 下列問題可協助您決定如何維護位置資料庫。

 **您將如何更新位置資料庫？**

有幾個案例需要更新位置資料庫，包括新增無線存取點 (Wap) 、office recabling (導致不同的切換指派) 及子網擴充。 您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？

 **您會使用 SNMP 應用程式，將商務用 Skype 用戶端 MAC 位址與埠及切換識別碼相符嗎？**

如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。 如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。