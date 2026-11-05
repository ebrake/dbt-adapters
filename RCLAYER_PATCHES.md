# RecruitLayer patches

The `dbt-adapters` wheel omits `dbt/include/__init__.py`. `dbt-core` ships the
same `pkgutil.extend_path` initializer, and pnpm's Python installer rejects
duplicate wheel paths even when their contents are identical. The file remains
available from `dbt-core` in the supported installation graph.
