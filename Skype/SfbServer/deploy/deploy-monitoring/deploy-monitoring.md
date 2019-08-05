---
title: 在商務用 Skype Server 中部署監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: '摘要: 瞭解如何在商務用 Skype Server 中部署監視。'
ms.openlocfilehash: bd194e8f39130de7a02a56afa2fa1f82bb662c76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189481"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>在商務用 Skype Server 中部署監視

**摘要:** 瞭解如何在商務用 Skype Server 中部署監視。

在執行這些工作之前, 請先[在商務用 Skype Server 中審查監視方案](../../plan-your-deployment/monitoring.md)。

您通常會透過完成下列兩個步驟來在拓撲內執行監視服務:

1. 在您設定新的商務用 Skype 伺服器池時啟用監視。 (在商務用 Skype Server 中, 在每個池中分別啟用或停用監視。)請注意, 您可以在不實際收集監視資料的情況下啟用對某個池的監視, 在本檔的 [設定呼叫詳細資料記錄] 和 [經驗品質設定] 區段中說明的程式。

2. 將監視存放區 (即監視資料庫) 與新的池建立關聯。 請注意, 單一監視存儲可以與多個池建立關聯。 根據您的註冊機構池中駐留的使用者數目而定, 這表示您不需要為每個池設定個別的監視資料庫。 相反地, 單一監視存放區可以由多個池使用。

雖然在您建立新的資料庫池的同時啟用監視通常是比較容易的, 但是也可以建立一個已停用監視的新池。 如果您這樣做, 您可以在稍後使用拓撲建立器來啟用服務: [拓撲建立器] 提供啟用或停用池監視的方式, 或將池與不同的監視存放區建立關聯。 請記住, 即使不再有監視伺服器角色, 您仍需建立一或多個監視存儲: 後端資料庫, 用來儲存由監視服務收集的資料。 您可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012 或 Microsoft SQL Server 2014 來建立這些後端資料庫。

> [!NOTE]
> 如果已針對某個池啟用監視, 您可以停用收集監控資料的程式, 而不需變更您的拓撲: 商務用 Skype Server 提供一種方式, 讓您可以停用 (然後重新啟用) 通話詳細資料錄製 (CDR) 或品質體驗 (QoE) 資料收集。 如需詳細資訊, 請參閱本檔的設定通話詳細資料錄製和體驗設定一節。

在商務用 Skype Server 中進行監控的另一個重要增強功能, 就是商務用 Skype Server 監視報告現在支援 IPv6: 使用 [IP 位址] 欄位的報表會顯示 IPv4 或 IPv6 位址 (視情況而定): 1) SQL 查詢使用中;與, 2) IPv6 位址儲存在監視資料庫中的位置。

> [!NOTE]
> 確定 SQL Server Agent 服務啟動類型為 [自動], 且 SQL Server Agent 服務正在針對擁有監視資料庫的 SQL 實例執行, 因此預設的監視 SQL Server 維護作業可以依排程的方式執行[SQL Server 代理程式服務] 的控制權。

本檔會逐步引導您完成安裝及設定商務用 Skype Server 的監視及監視報告的程式。 本檔提供可協助您執行下列逐步指示:

- 在拓撲中啟用監視, 並將監視存放區與前端池建立關聯。

- 安裝 SQL Server Reporting Services 及商務用 Skype Server 監視報告。 監視報告是預先配置的報告, 可為監視資料庫中儲存的資訊提供不同的視圖。

- 設定通話詳細資料錄製 (CDR) 和體驗品質 (QoE) 資料收集。 通話詳細資料錄製提供一種方式, 讓您追蹤商務用 Skype 伺服器功能 (例如, 語音 over IP (VoIP) 電話通話) 的使用方式;立即訊息 (IM);檔案傳輸;音訊/視頻 (A/V) 會議;與應用程式共用會話。 QoE 度量單位會追蹤您組織中的音訊和視頻通話品質, 包括網路資料包遺失、背景雜色及「抖動」 (資料包延遲的差異) 等專案。

- 從監視資料庫手動清除 CDR 和/或 QoE 記錄。

## <a name="deployment-checklist-for-monitoring"></a>監控的部署檢查表

雖然已在每個前端伺服器上安裝並啟用監視, 但您仍必須採取幾個步驟, 才能實際收集商務用 Skype Server 的監視資料。 以下是下列檢查清單中所述的步驟:

|**分**|**步驟**|**角色與群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必備的硬體和軟體** <br/> |在電腦上安裝受支援的 Microsoft SQL Server 版本, 該電腦將充當要監視的後端資料存放區。  <br/> |同時也是本機管理員群組成員的網域使用者。  <br/> |[支援的硬體](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [伺服器軟體和基礎結構支援](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**建立適當的內部拓朴以支援監視** <br/> |使用商務用 Skype Server 拓撲建立器, 將監視資料庫新增到拓撲結構, 然後發佈更新後的拓撲。  <br/> |若要定義拓撲, 該使用者是 [本機使用者] 群組的成員。  <br/> 如果是 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組, 則會發佈拓撲 (屬於成員的使用者)。  <br/> |[在商務用 Skype Server 中, 將監控存放區與前端池建立關聯](associate-a-monitoring-store.md) <br/> |
|**啟用適當的監視設定** <br/> |啟用 [呼叫詳細資料錄製 (CDR)] 和/或 [(QoE)] 在全域及/或網站範圍內進行監控。  <br/> |是 RTCUniversalServerAdmins 群組成員的使用者, 或已被指派 RBAC 角色的使用者, 可提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 的存取權。  <br/> |[在商務用 Skype Server 中設定通話詳細資料錄製和經驗品質設定](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>啟用監視

雖然整合的資料收集代理程式會在每個前端伺服器上自動安裝並啟用, 這並不表示您會在完成商務用 Skype Server 的安裝之後, 自動開始收集監視資料。 相反地, 您必須執行兩個動作: 您必須將前端伺服器/前端池與監控資料庫建立關聯, 而且您必須啟用 [呼叫詳細資料錄製 (CDR)] 和/或 [(QoE)] (在全域範圍和/或網站範圍中) 的監視品質 ()。

如需將前端伺服器或頂層池與監視資料庫相關聯的逐步指示, 請參閱部署指南中[與商務用 Skype Server](associate-a-monitoring-store.md)中的 [前端] 池關聯的 [監視存儲] 主題。 建立這些關聯之後, 且在您新的商務用 Skype Server 拓撲發佈之後, 您仍然無法收集監視資料。 這是因為, 在您安裝商務用 Skype Server 時, 會停用 CDR 與 QoE 資料收集。

若要開始收集資料, 您需要啟用 CDR 和/或 QoE 監視。 (請注意, 您不需要同時啟用 CDR 與 QoE 監視; 如果您想要的話, 您可以啟用一種監視類型, 讓其他類型保持停用。)若要在全域範圍啟用 CDR 監視, 請從商務用 Skype Server Management Shell 中執行下列命令:

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

或者, 您可以從商務用 Skype Server 的 [控制台] 中啟用 CDR 監視。 在商務用 Skype Server 的 [控制台] 中, 完成下列程式:

1. 按一下 [**監視**]。

2. 在 [**通話詳細資料記錄**] 索引標籤上, 按兩下 [**全域**] 設定。

3. 在 [**編輯通話詳細資料錄製 (CDR)] 設定**窗格中, 選取 [**啟用 CDRs 監視**], 然後按一下 [**確認**]。

若要在全域範圍啟用 QoE 監視, 請在商務用 Skype Server Management Shell 中執行此命令:

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果您想要的話, 您也可以在商務用 Skype Server 的 [控制台] 中啟用 QoE 監視。 從 [控制] 面板中, 完成下列程式:

1. 按一下 [**監視**]。

2. 在 [**體驗品質**] 的 [資料] 索引標籤上, 按兩下 [**全域**] 設定。

3. 在 [**編輯體驗品質 (QoE)] 設定**窗格中, 選取 [**啟用 QoE 資料的監視**], 然後按一下 [**確認**]。

如前所述, 前面的範例可在全域範圍內啟用監視;也就是說, 它們可在整個組織中啟用 CDR 與 QoE 監視。 或者, 您可以在網站範圍中建立個別的 CDR 及 QoE 設定設定, 然後有選擇性地針對每個網站啟用或停用監視。 例如, 您可以為雷德蒙的網站啟用 CDR 監視, 但卻停用了您的都柏林網站的 CDR 監視。 如需管理監視設定設定的詳細資訊, 請參閱部署指南主題[設定商務用 Skype Server 中的呼叫詳細資料錄製和經驗品質設定](call-detail-recording-and-qoe.md)。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中規劃監視](../../plan-your-deployment/monitoring.md)
