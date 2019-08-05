---
title: 商務用 Skype Server 中的災害復原測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 針對商務用 Skype 伺服器池伺服器執行系統復原, 以測試您已記錄的災害復原程式
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188497"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>商務用 Skype Server 中的災害復原測試

針對商務用 Skype 伺服器池伺服器執行系統復原, 以測試您已記錄的災害復原程式。 這個測試將會模擬一台伺服器的完整硬體故障, 並將協助保證資源、方案及資料可供恢復使用。 請嘗試每月變換測試重點，以便您組織每次都能測試不同伺服器的故障狀況或設備的其他部件。 

請注意，組織執行災害復原測試的排程各不相同，切勿忽略或疏於進行災害復原測試。 

將商務用 Skype 伺服器拓撲、原則和設定設定匯出至檔案。 除此之外，在升級、發生硬體故障或某些其他問題而造成資料遺失之後，此檔案還可在用於將此資訊還原至中央管理存放區。

將商務用 Skype 伺服器拓朴、原則和設定的設定匯入到中央管理商店或本機電腦上, 如下列命令所示: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

若要備份生產資料:

- 使用標準的 SQL Server 備份程式將資料庫轉儲至檔案或磁帶轉儲裝置, 以備份 RTC 及 LCSLog 資料庫。
- 使用協力廠商備份應用程式，將資料備份至檔案或磁帶。
- 使用 Export-CsUserData cmdlet 來建立整個 RTC 資料庫的 XML 匯出。
- 使用檔案系統備份或協力廠商備份來備份會議內容和合規性記錄。
- 使用 Export CsConfiguration 命令列工具來備份商務用 Skype Server 設定。

容錯移轉程序的第一步驟包含將使用者從生產集區強制移至災害復原集區。 此一步驟將為強制移動，因為生產集區將無法接受使用者遷移。

除了 RTC SQL 資料庫上的記錄更新之外, 商務用 Skype Server 移動使用者程式也會對使用者帳戶物件上的屬性有實際的變更。 您可以使用標準的 SQL Server 還原程式, 或使用協力廠商的備份/還原公用程式, 從生產 SQL Server 上的原始備份轉儲裝置還原此資料。

還原此資料之後, 使用者就能有效地連線到災害復原池, 並正常運作。 若要讓使用者能夠連線到災害復原池, 就必須變更 DNS 記錄。

用戶端將會使用自動設定和 DNS SRV 記錄來參照商務用 Skype 泳池池:

- SRV: _sip. _tls。\<網域>/CNAME: SIP。\<網域>
- CNAME: SIP。\<網域>/cvc-pool-1。\<網域>

若要輔助容錯移轉，必須更新這項 CNAME 記錄才能參考 DROCSPool FQDN：

- CNAME: SIP。<domain> /DROCSPool.\<網域>
- 呼吸.\<網域>
- AV.\<網域>
- webconf.\<網域>
