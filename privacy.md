---
layout: default
title: 隐私权政策
---

# 隐私权政策

应用：china-brand-leads-backup  
维护者：[Yu-RJI](https://github.com/Yu-RJI)  
更新日期：2026-10-19

## 访问的数据和用途

本个人应用通过 Google 的 `drive.file` 权限，访问本应用创建或经使用者明确授权的特定文件。涉及的数据包括这些文件的名称、标识、共享权限、内容和更新时间，以及维持授权所需的访问凭据与刷新凭据。

应用将经过审核的企业公开商务联系信息及其来源写入使用者的 Google Sheets，并读回这些单元格以检查写入结果、避免重复。结果包含企业、品牌、官网、公开商务邮箱、来源证据、审核结论及交付日期。

应用在专用 Google Drive 目录保存数据库备份，并下载自己的备份进行完整性校验与独立恢复。备份包含企业、联系人、来源、候选、审核、搜索费用、访问限制、执行和历史交付记录，用于恢复系统及防止重复交付。

Google 授权范围不包含 Gmail、通讯录或完整 Drive 访问。Google 文件内容仅用于上述同步、备份、校验及恢复功能，不用于广告、出售数据或训练通用人工智能模型。

## 存储和处理

应用由使用者在自己的电脑和私有 GitHub Actions 环境中运行。Google OAuth 凭据保存在本地安全配置及 GitHub Secrets 中，不写入公开代码或运行日志。Google 文件和授权信息通过 HTTPS 传输。

数据库保存在使用者控制的 Supabase 项目中。数据库备份上传到 Google Drive 前使用 AES-256-GCM 认证加密，解密密钥另行保存在使用者的本地安全配置和 GitHub Secrets 中。恢复校验会在独立 PostgreSQL 环境短暂生成解密文件，校验结束后清理该临时环境。

Google Sheets 中的业务结果以可阅读的表格形式保存，访问权限由使用者的 Google 账户管理。表格和备份默认仅供所有者访问。

GitHub、Google 和 Supabase 分别提供执行、文件保存和数据库服务。应用仅在实现上述功能所需的范围内向这些服务传输数据。公开企业检索使用 Tavily；应用不向 Tavily 发送 Google 文件内容或 Google 授权凭据。

本说明网站计划使用 GitHub Pages 托管。GitHub 会为安全目的记录访问者的 IP 地址等访问日志，具体处理见 [GitHub 隐私声明](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement)。说明页不设置额外的广告或分析脚本。

## 保留、删除和撤销授权

正式交付及去重历史长期保存，以避免再次交付同一企业。备份保留策略为最近 30 份日备份和最近 12 份月备份。只有新备份下载校验成功后，才清理本项目超出保留范围的旧备份。

使用者可以在 [Google 账户的第三方连接](https://myaccount.google.com/connections) 中撤销应用授权。撤销后应用无法继续访问 Google 文件，但已创建的文件会保留在使用者的账户内，直到使用者自行删除。停止使用时，使用者可以停用 GitHub 自动任务，删除本地与 GitHub 中的授权凭据，并按自己的保留要求处理表格、备份和数据库。

## 数据使用承诺

应用对从 Google API 获取的信息的使用和传输遵循 [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy)，包括适用的 Limited Use 要求。对数据访问或用途作实质变更时，将先更新本政策并重新取得必要授权。

## 联系

维护者为 [Yu-RJI](https://github.com/Yu-RJI)。需要处理授权或数据问题时，可使用 Google 授权页面显示的开发者联系邮箱。请通过私密渠道处理含个人数据的请求，勿在公开页面发送密码、凭据或备份内容。

[返回应用首页](index.html)
