# To update build version
bumpver update --minor

# Build package
python -m build

# Test package
twine check dist/*

# Push package to pypi
twine upload -r testpypi dist/*
twine upload dist/*
