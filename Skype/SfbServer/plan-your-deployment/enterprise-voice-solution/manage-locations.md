---
title: 在商務用 Skype Server 中管理 SIP 中繼服務提供者的位置
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 在商務用 Skype Server Enterprise Voice 中使用 SIP 中繼提供者來規劃位置資訊資料庫或類似的外部資料庫, 以進行規劃的 E9。
ms.openlocfilehash: aafe35f4978ac18897d11aa55f229df501d555ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187636"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 SIP 中繼服務提供者的位置

在商務用 Skype Server Enterprise Voice 中使用 SIP 中繼提供者來規劃位置資訊資料庫或類似的外部資料庫, 以進行規劃的 E9。

若要設定商務用 Skype Server 自動在網路中尋找用戶端, 您必須使用網路 wiremap 填入位置資訊服務資料庫, 然後發佈位置, 或連結到已包含的外部資料庫正確的對應。 作為此程式的一部分, 您必須使用 E9-1 服務提供者驗證位置的市政位址。 如需詳細資訊, 請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。

您可以使用緊急回應位置 (ERL) 來填入位置資訊服務資料庫, 這是由市政位址以及建築物內的特定位址所組成。 [位置資訊服務**位置**] 欄位是建築物內的特定位置, 最大長度為20個字元 (包括空格)。 在該長度有限的範圍內, 嘗試包含下列專案:

- 識別911呼叫者位置的易於理解的名稱, 可協助確保緊急回應程式在到達市政位址時能快速找到特定位置。 這個位置名稱可以包含建築物編號、樓層編號、翼標示符、房間號碼等。 避免只有員工知道別名, 這可能會導致緊急回應程式移至錯誤的位置。

- 此位置識別碼可協助使用者輕鬆查看其商務用 Skype 用戶端是否已挑選正確的位置。 商務用 Skype 用戶端會自動連接並在其標題中顯示 [已探索的**位置**] 和 [**城市**] 欄位。 最佳做法是將建築物的街道位址新增至每個位置識別碼 (例如, "1 層<street number>")。 如果沒有街道位址, 一般位置識別碼 (例如「第一層」) 會套用至城市中的任何建築物。

- 如果該位置是由無線存取點決定, 您可以新增 **[靠近]** (例如, 「接近第一層樓1234」) 中的單字。

> [!NOTE]
> 除非您使用商務用 Skype Server Management Shell 命令發佈並複製到該池的本機存儲區, 否則用戶端不能使用新增到中央位置資料庫的位置。 如需詳細資訊, 請參閱在部署檔中[發佈位置資料庫](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。

下列各節討論當您填入及維護位置資料庫時需要考慮的事項。

## <a name="populating-the-location-database"></a>填充位置資料庫

下列問題可協助您決定如何填入位置資料庫。

 **您將使用哪個程式來填入位置資料庫？**

資料在哪裡存在, 您需要採取哪些步驟才能將資料轉換成位置資料庫所需的格式？ 您會使用 CSV 檔案個別地新增位置, 還是大量新增位置？

 **您是否有已包含位置對應的協力廠商資料庫？**

透過使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫, 您可以使用離線平臺來分組及管理位置。 這種方法的優點是, 除了將位置與網路識別碼相關聯之外, 您還可以將位置與使用者建立關聯。 這表示位置資訊服務可以傳回多個位址 (源自次要位置資訊服務) 到商務用 Skype 用戶端。 然後, 使用者可以選擇最適合的位置。

若要整合位置資訊服務, 協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。 如需詳細資訊, 請參閱[[[MS-E911WS]: 適用于 E911 的 Web 服務支援通訊協定規格](https://go.microsoft.com/fwlink/p/?linkid=213819)」。 如需有關部署次要位置資訊服務的詳細資訊, 請參閱在部署檔中的[商務用 Skype Server 中設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。

如需有關填充位置資料庫的詳細資訊, 請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。

## <a name="maintaining-the-location-database"></a>維護位置資料庫

在您填入 location 資料庫之後, 您需要開發一個策略, 在網路設定變更時更新資料庫。 下列問題將協助您決定如何維護位置資料庫。

 **如何更新位置資料庫？**

有幾種情況需要更新位置資料庫, 包括新增 WAPs、office recabling (產生不同的切換作業), 以及子網延伸。 您是否會直接更新每個個別位置, 或是使用 CSV 檔案執行所有位置的大量更新？

 **您會使用 SNMP 應用程式, 將 Lync 用戶端 MAC 位址與埠和交換器識別碼搭配使用嗎？**

如果您使用的是 SNMP 應用程式, 您必須開發手動程式, 以保持 SNMP 應用程式和位置資料庫之間的切換底盤和埠資訊一致。 如果 SNMP 應用程式傳回的是不包含在資料庫中的主機殼 IP 位址或埠 ID, 位置資訊服務將無法傳回用戶端的位置。


