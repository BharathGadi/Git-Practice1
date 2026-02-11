# Git Reset - Step by Step Learning Guide

## Overview

This guide will teach you how to use `git reset` to undo commits. We'll:

1. Make changes and commit them
2. Push to remote
3. Learn different types of `git reset`
4. Revert the changes

## Step 1: Make Some Changes

We'll modify existing files to create commits.

## Step 2: Stage and Commit Changes

```bash
git add .
git commit -m "Learning git reset - added new features"
```

## Step 3: Push to Remote

```bash
git push origin main
```

## Step 4: Understanding Git Reset

### Types of Git Reset:

#### 1. `git reset --soft HEAD~1`

- **What it does**: Moves the branch pointer back, but keeps changes staged
- **Use case**: When you want to recommit with a different message
- **Changes**: Commits are undone, but files remain staged

#### 2. `git reset --mixed HEAD~1` (or just `git reset HEAD~1`)

- **What it does**: Moves the branch pointer back, unstages changes, but keeps them in working directory
- **Use case**: When you want to undo a commit but keep the changes to modify
- **Changes**: Commits are undone, files are unstaged but still modified

#### 3. `git reset --hard HEAD~1`

- **What it does**: Moves the branch pointer back and discards all changes
- **Use case**: When you want to completely remove commits and changes
- **Warning**: This permanently deletes your changes!

## Step 5: Reverting After Push

After pushing, you have two options:

### Option A: Reset and Force Push (⚠️ Use with caution!)

```bash
git reset --hard HEAD~1
git push --force origin main
```

**Warning**: Force push rewrites history. Only use if you're sure no one else has pulled your changes!

### Option B: Create a Revert Commit (Safer)

```bash
git revert HEAD
git push origin main
```

This creates a new commit that undoes the previous one - safer for shared branches.

## What We'll Do

We'll demonstrate `git reset --mixed` (the most common) and show you how to handle the remote.
