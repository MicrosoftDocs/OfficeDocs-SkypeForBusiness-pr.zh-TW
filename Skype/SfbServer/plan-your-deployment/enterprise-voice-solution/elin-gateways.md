---
title: 在商務用 Skype Server 中管理 ELIN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 在商務用 Skype Server Enterprise Voice 中使用 ELIN 閘道部署的位置資訊資料庫, 或類似的外部資料庫來規劃 E9。
ms.openlocfilehash: e1645be8ed1c6188d1976d794727d0668b79c12e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187717"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 ELIN 閘道的位置

在商務用 Skype Server Enterprise Voice 中使用 ELIN 閘道部署的位置資訊資料庫, 或類似的外部資料庫來規劃 E9。

若要讓商務用 Skype 伺服器自動為網路中的用戶端提供位置, 您必須執行下列工作:

- 使用網路 wiremap 填入位置資訊服務資料庫, 並在 [公司名稱] 欄位中包含緊急位置識別號碼 (ELINs)。

- 發佈位置, 讓您的網路上的客戶可以使用它們。

- 將 ELINs 上傳到您的公用交換電話網絡 (PSTN) 電信公司的自動位置識別 (阿裡) 資料庫。

如需如何執行這些工作的詳細資訊, 請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。

> [!NOTE]
> 除非已使用商務用 Skype Server Management Shell 命令發佈並複製到該池的本機存儲區, 否則用戶端不能使用新增到中央位置資料庫的位置。 如需詳細資訊, 請參閱在部署檔中[發佈位置資料庫](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。

本節說明您規劃更新及維護位置資料庫時應考慮的事項。

## <a name="planning-emergency-locations"></a>規劃緊急位置

當您使用 ELIN 閘道時, 您會使用市政位址、組建中的特定位置, 以及為每個位置至少一個 ELIN 來填入位置資訊服務資料庫。 在規劃階段, 最好決定您要如何命名位置, 以及您想要如何指派 ELINs。

### <a name="planning-location-names"></a>規劃位置名稱

[位置資訊服務**位置**] 欄位會存放建築物內的特定位置, 最大長度為20個字元 (包括空格)。 在該長度有限的範圍內, 嘗試包含下列專案:

- 識別911呼叫者位置的易於理解的名稱, 可協助確保緊急回應程式在到達市政位址時能快速找到特定位置。 這個位置名稱可以包含建築物編號、樓層編號、翼標示符、房間號碼等。 避免只提供給員工的昵稱, 這可能會導致緊急回應程式移至錯誤的位置。

- 可協助使用者輕鬆查看其用戶端挑選正確位置的位置識別碼。 商務用 Skype 用戶端會自動連接並在其標題中顯示 [已探索的**位置**] 和 [**城市**] 欄位。 最佳做法是將建築物的街道位址新增至每個位置識別碼 (例如, "1 層<street number>")。 如果沒有街道位址, 一般位置識別碼 (例如「第一層」) 會套用至城市中的任何建築物。

- 如果該位置是由無線存取點決定, 您可能會想要新增 **[靠近]** (例如, "靠近1層樓 1234") 的字。

### <a name="planning-elins"></a>規劃 ELINs

在您決定要如何將建築物空間劃分至多個位置之後, 您必須決定要將多少 ELINs 指派給每個位置。 例如, 在 multifloor 或多租戶組建中, 組建中的不同區域可以指定不同的緊急區域。 一般來說, 建築物中的每個樓層都指定為一個位置。 接著, 系統會為每個位置指派一個或多個 ELINs, 在緊急通話期間, 就會用來做為電話號碼。 請與您的 PSTN 運營商聯繫, 以取得您可以用來 ELINs 的電話號碼。 下表提供特定街道位址的位置範例。

**範例位置與 ELIN 作業**

|**建築物區域**|**位置**|**ELIN**|
|:-----|:-----|:-----|
|第一層  <br/> |sr-1  <br/> |425-555-0100  <br/> |
|第二層  <br/> |pplx-2  <br/> |425-555-0111  <br/> |
|第三層  <br/> |3  <br/> |425-555-0123  <br/> |

您定義的位置應該符合下列需求:

- 在每個位置的最大區域及每個街道位址的位置數方面, 遵守當地和國家/地區管理法規。

- 都有足夠的針對性, 便於您找到緊急來電者。

## <a name="populating-the-location-database"></a>填充位置資料庫

下列問題將協助您決定將如何填入位置資料庫。

 **您將使用哪個程式來填入位置資料庫？**

資料在哪裡存在, 您需要採取哪些步驟才能將資料轉換成位置資料庫所需的格式？ 您會使用 CSV 檔案個別地新增位置, 還是大量新增位置？

 **您是否有已包含位置對應的協力廠商資料庫？**

透過使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫, 您可以使用離線平臺來分組及管理位置。 這種方法的優點是, 除了將位置與網路識別碼相關聯之外, 您還可以將位置與使用者建立關聯。 這表示位置資訊服務可以傳回多個位址 (源自次要位置資訊服務) 到商務用 Skype 用戶端。 然後, 使用者可以選擇最適合的位置。

若要整合位置資訊服務, 協力廠商資料庫必須遵循商務用 Skype Server 位置要求/回應架構。 如需詳細資訊, 請參閱[Web 服務以取得 E911 支援通訊協定](https://go.microsoft.com/fwlink/p/?linkid=213819)。 如需有關部署次要位置資訊服務的詳細資訊, 請參閱在部署檔中的[商務用 Skype Server 中設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。

如需有關填充位置資料庫的詳細資訊, 請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。

## <a name="maintaining-the-location-database"></a>維護位置資料庫

在您填入 location 資料庫之後, 您需要開發一個策略, 在網路設定變更時更新資料庫。 下列問題將協助您決定如何維護位置資料庫。

 **如何更新位置資料庫？**

有幾種情況需要更新位置資料庫, 包括新增無線存取點 (WAPs)、office recabling (產生不同的切換作業), 以及子網延伸。 您是否會直接更新每個個別位置, 或是使用 CSV 檔案執行所有位置的大量更新？

 **您是否會使用 SNMP 應用程式, 將商務用 Skype 用戶端 MAC 位址與埠和切換識別碼相符？**

如果您使用的是 SNMP 應用程式, 您必須開發手動程式, 以保持 SNMP 應用程式和位置資料庫之間的切換底盤和埠資訊一致。 如果 SNMP 應用程式傳回的是不包含在資料庫中的主機殼 IP 位址或埠 ID, 位置資訊服務將無法傳回用戶端的位置。


