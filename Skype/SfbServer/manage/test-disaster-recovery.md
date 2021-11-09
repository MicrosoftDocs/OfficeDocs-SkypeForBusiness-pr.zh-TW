---
title: 商務用 Skype Server 中的災難修復測試
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 為商務用 Skype Server 集區伺服器執行系統復原，以測試已記錄的災難修復程式
ms.openlocfilehash: 2d6fa097061b470814887f1e13eaf4748de6e4f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863500"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>商務用 Skype Server 中的災難修復測試

為商務用 Skype Server 集區伺服器執行系統復原，以測試您已記錄的災難修復程式。 這項測試會模擬一部伺服器的完整硬體故障，並協助保證資源、計畫及資料可用於復原。 嘗試每月旋轉測試的焦點，使組織每次測試不同伺服器或其他裝置的失敗。 

請注意，組織執行嚴重損壞修復測試的排程會有所不同。 不會忽視或忽略嚴重損壞修復測試，這一點很重要。 

將商務用 Skype Server 拓撲、原則及設定設定匯出至檔案。 除此之外，您也可以使用此檔案在升級、硬體故障或其他問題導致資料遺失的情況下，將此資訊還原至中央管理存放區。

將商務用 Skype Server 拓撲、原則和設定設定匯入中央管理存放區或本機電腦，如下列命令所示： 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

若要備份實際執行資料：

- 使用標準 SQL Server 備份程式備份 RTC 和 LCSLog 資料庫，以將資料庫轉儲至檔案或磁帶轉儲裝置。
- 使用協力廠商備份應用程式將資料備份至檔案或磁帶。
- 使用 Export-CsUserData Cmdlet 來建立整個 RTC 資料庫的 XML 匯出。
- 使用檔案系統備份或協力廠商備份來備份會議內容和合規性記錄。
- 使用 Export-CsConfiguration 命令列工具來備份商務用 Skype Server 設定。

容錯移轉程式中的第一個步驟包括將使用者從生產集區強制移至嚴重損壞修復集區。 這將會強制移動，因為實際生產集區無法接受使用者重新安置。

除了 RTC SQL 資料庫上的記錄更新之外，商務用 Skype Server 的移動使用者程式也會變更使用者帳戶物件上的屬性。 您可以使用標準 SQL Server 還原程式，或使用協力廠商備份/還原公用程式，從生產 SQL Server 還原原始備份轉儲裝置的資料。

還原此資料之後，使用者就能有效地連接至災害復原集區，並照常運作。 若要讓使用者能夠連線至災害復原集區，將需要 DNS 記錄變更。

使用的自動設定和 DNS SRV 記錄，用戶端將會參考生產商務用 Skype 集區：

- SRV： _sip _tls。\<domain> /CNAME： SIP。\<domain>
- CNAME： SIP。\<domain> /cvc-pool-1.\<domain>

若要協助容錯移轉，必須更新此 CNAME 記錄，以參考 DROCSPool FQDN：

- CNAME： SIP。\<domain> /DROCSPool.\<domain>
- Sip。\<domain>
- AV。\<domain>
- webconf.\<domain>
